
```chartsview
# 1. 定义图表类型为词云图
type: WordCloud

# 2. 配置图表选项
options:
  wordField: "word"
  weightField: "count"
  colorField: "word"
  wordStyle:
    rotation: 0

# 3. 使用 dataviewjs 动态查询和处理数据
data: |
  dataviewjs:
  // 步骤 a: 定义停用词列表
  const stopWords = new Set([
    'x', 'daily-note', 'date', 'tags', 'mood', 'and', 'the', 'to', 'a', 'in', 'of',
    '---'
  ]);

  // 步骤 b: 查询 'diary' 文件夹
  const pages = dv.pages('"diary"');
  
  // 步骤 c: 合并所有文本
  let allText = "";
  for (const page of pages) {
    const content = await dv.io.load(page.file.path);
    allText += content + "\n";
  }

  // 步骤 d: 分词和词频统计
  const wordCounts = {};
  const words = allText.match(/[\p{L}\p{N}_-]+/gu) || [];

  for (const word of words) {
    const lowerWord = word.toLowerCase();
    
    // 步骤 d.1 (新增): 检查当前单词是否是 YYYY-MM-DD 格式的日期
    const isDate = /^\d{4}-\d{2}-\d{2}$/.test(lowerWord);
    
    // 步骤 d.2 (修改): 在原有条件基础上，增加“不是日期”的判断
    if (!stopWords.has(lowerWord) && lowerWord.length > 1 && !isDate) {
        wordCounts[lowerWord] = (wordCounts[lowerWord] || 0) + 1;
    }
  }
  
  // 步骤 e: 转换格式
  const chartData = Object.entries(wordCounts).map(([word, count]) => ({
    word: word,
    count: count
  }));

  // 步骤 f: 返回最终数据
  return chartData;
```



```chartsview
# 1. 定义图表类型为词云图
type: WordCloud

# 2. 配置图表选项
options:
  wordField: "word"
  weightField: "count"
  colorField: "word"
  wordStyle:
    rotation: 0

# 3. 使用 dataviewjs 动态查询和处理数据
data: |
  dataviewjs:
  // 步骤 a (修改): 扩充停用词列表，加入更多无意义的词
  const stopWords = new Set([
    'x', 'daily-note', 'date', 'tags', 'mood', '喝水', '回顾', '今日',
    '明日', '计划', '习惯', '打卡', 'and', 'the', 'to', 'a', 'in', 'of',
    '---', 'is', 'by', 'on', 'me', 'for', 'are', 'with', 'this', 'site'
  ]);

  // 步骤 b: 查询所有文件，但排除 "diary" 文件夹
  const pages = dv.pages('-"diary"');
  
  // 步骤 c: 异步读取所有文件内容，并进行清洗
  let allText = "";
  for (const page of pages) {
    const rawContent = await dv.io.load(page.file.path);

    // 步骤 c.1 (核心修改): 使用更强力的清洗规则
    const cleanedContent = rawContent
      // 1. 移除 YAML frontmatter
      .replace(/^---\s*[\s\S]*?---\s*/, '')
      // 2. 移除所有代码块
      .replace(/```[\s\S]*?```/g, '')
      // 3. (新) 移除所有网址链接
      .replace(/https?:\/\/[^\s]+/g, '')
      // 4. (新) 将任何连续3个以上的分割线符号替换为空格
      //    这会处理 ---列表项--- 这样的情况，把它变成 列表项
      .replace(/(-|\*|_){3,}/g, ' ');

    allText += cleanedContent + "\n";
  }

  // 步骤 d: 分词和词频统计
  const wordCounts = {};
  const words = allText.match(/[\p{L}\p{N}_-]+/gu) || [];

  for (const word of words) {
    const lowerWord = word.toLowerCase();
    const isDate = /^\d{4}-\d{2}-\d{2}$/.test(lowerWord);
    
    // (新增) 再次过滤完全由连字符组成的残留词
    const isJustHyphens = /^-+$/.test(lowerWord);

    if (!stopWords.has(lowerWord) && lowerWord.length > 1 && !isDate && !isJustHyphens) {
        wordCounts[lowerWord] = (wordCounts[lowerWord] || 0) + 1;
    }
  }
  
  // 步骤 e: 转换格式
  const chartData = Object.entries(wordCounts).map(([word, count]) => ({
    word: word,
    count: count
  }));

  // 步骤 f: 返回最终数据
  return chartData;
```