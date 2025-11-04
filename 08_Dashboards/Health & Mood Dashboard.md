

## 📊 All Activity

```dataviewjs
const pages = dv.pages('"01_Daily"')
  .where(p => p.pushups != null || p.mood != null)
  .sort(p => p.created, 'desc');

const pushupsArray = pages.where(p => p.pushups != null).map(p => p.pushups).array();
const moodArray = pages.where(p => p.mood != null).map(p => p.mood).array();

const avgPushups = pushupsArray.length > 0 ? (pushupsArray.reduce((a, b) => a + b, 0) / pushupsArray.length).toFixed(1) : 0;
const avgMood = moodArray.length > 0 ? (moodArray.reduce((a, b) => a + b, 0) / moodArray.length).toFixed(1) : 0;

dv.table(
  ["Date", "Pushups", "Mood", "Avg Pushups", "Avg Mood"],
  pages.map(p => [
    p.file.name,
    p.pushups || "-",
    p.mood || "-",
    avgPushups,
    avgMood
  ])
);
```

## 📈 Pushups Progress

```dataviewjs
const pages = dv.pages('"01_Daily"')
  .where(p => p.pushups != null)
  .sort(p => p.created, 'desc');

const pushupsArray = pages.map(p => p.pushups).array();
const avgPushups = pushupsArray.length > 0 ? (pushupsArray.reduce((a, b) => a + b, 0) / pushupsArray.length).toFixed(1) : 0;

dv.table(
  ["Date", "Pushups", "Avg Pushups"],
  pages.map(p => [
    p.file.name,
    p.pushups,
    avgPushups
  ])
);
```

## 😊 Mood Tracking

```dataviewjs
const pages = dv.pages('"01_Daily"')
  .where(p => p.mood != null)
  .sort(p => p.created, 'desc');

const moodArray = pages.map(p => p.mood).array();
const avgMood = moodArray.length > 0 ? (moodArray.reduce((a, b) => a + b, 0) / moodArray.length).toFixed(1) : 0;

dv.table(
  ["Date", "Mood", "Avg Mood"],
  pages.map(p => [
    p.file.name,
    p.mood,
    avgMood
  ])
);
```

## 📅 This Week

```dataviewjs
const today = new Date();
const currentWeek = today.toISOString().slice(0, 4) + '-W' + 
  String(Math.ceil((today - new Date(today.getFullYear(), 0, 1)) / 86400000 / 7)).padStart(2, '0');

const pages = dv.pages('"01_Daily"')
  .where(p => p.week === currentWeek && (p.pushups != null || p.mood != null))
  .sort(p => p.created, 'desc');

const pushupsArray = pages.where(p => p.pushups != null).map(p => p.pushups).array();
const moodArray = pages.where(p => p.mood != null).map(p => p.mood).array();

const avgPushups = pushupsArray.length > 0 ? (pushupsArray.reduce((a, b) => a + b, 0) / pushupsArray.length).toFixed(1) : 0;
const avgMood = moodArray.length > 0 ? (moodArray.reduce((a, b) => a + b, 0) / moodArray.length).toFixed(1) : 0;

if (pages.length > 0) {
  dv.table(
    ["Date", "Pushups", "Mood", "Avg Pushups", "Avg Mood"],
    pages.map(p => [
      p.file.name,
      p.pushups || "-",
      p.mood || "-",
      avgPushups,
      avgMood
    ])
  );
} else {
  dv.paragraph("No data for this week yet.");
}
```

## 📉 Weekly Summary

```dataviewjs
const pages = dv.pages('"01_Daily"')
  .where(p => p.pushups != null || p.mood != null);

const weeklyData = {};
pages.forEach(p => {
  const week = p.week || 'Unknown';
  if (!weeklyData[week]) {
    weeklyData[week] = { pushups: [], mood: [] };
  }
  if (p.pushups != null) weeklyData[week].pushups.push(p.pushups);
  if (p.mood != null) weeklyData[week].mood.push(p.mood);
});

const weeks = Object.keys(weeklyData).sort().reverse();
const rows = weeks.map(w => {
  const pushups = weeklyData[w].pushups;
  const mood = weeklyData[w].mood;
  const totalPushups = pushups.reduce((a, b) => a + b, 0);
  const avgPushups = pushups.length > 0 ? (totalPushups / pushups.length).toFixed(1) : 0;
  const avgMood = mood.length > 0 ? (mood.reduce((a, b) => a + b, 0) / mood.length).toFixed(1) : 0;
  
  return [w, totalPushups, avgPushups, avgMood];
});

dv.table(
  ["Week", "Total Pushups", "Avg Pushups", "Avg Mood"],
  rows
);
```

## 📊 Summary Statistics

```dataviewjs
const pages = dv.pages('"01_Daily"')
  .where(p => p.pushups != null || p.mood != null);

const pushupsPages = pages.where(p => p.pushups != null);
const moodPages = pages.where(p => p.mood != null);

const pushupsArray = pushupsPages.map(p => p.pushups).array();
const moodArray = moodPages.map(p => p.mood).array();

const totalPushups = pushupsArray.reduce((a, b) => a + b, 0);
const avgPushups = pushupsArray.length > 0 ? (totalPushups / pushupsArray.length).toFixed(1) : 0;
const moodSum = moodArray.reduce((a, b) => a + b, 0);
const avgMood = moodArray.length > 0 ? (moodSum / moodArray.length).toFixed(1) : 0;
const totalDays = pages.length;

dv.paragraph(`
**Total Pushups:** ${totalPushups}  
**Average Pushups/Day:** ${avgPushups}  
**Average Mood:** ${avgMood}/10  
**Days Tracked:** ${totalDays}
`);
```


