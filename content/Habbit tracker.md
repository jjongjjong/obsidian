

```dataviewjs
dv.span("**🏋️ 운동25분 🏋️**")

const calendarData = {
    colors: {
        red: ["#ff9e82","#ff7b55","#ff4d1a","#e73400","#bd2a00",]
    },
    entries: []
}

for(let page of dv.pages('"obsidian_repo/Planner/Daily"').where(p=>p.맨몸운동20분)){
    calendarData.entries.push({
        date: page.file.name,
        intensity: page.맨몸운동20분,
        content: await dv.span(`[](${page.file.name})`), //for hover preview
    })
       
}

renderHeatmapCalendar(this.container, calendarData)

```
```dataviewjs
dv.span("** 📚 독서10분 **")

const calendarData = {
    colors: {
        red: ["#ff7b55","#ff9e82","#ff4d1a","#e73400","#e73400",]
    },
    entries: []
}

for(let page of dv.pages('"obsidian_repo/Planner/Daily"').where(p=>p.독서10분)){
    calendarData.entries.push({
        date: page.file.name,
        intensity: page.독서10분,
        content: await dv.span(`[](${page.file.name})`), //for hover preview
    })
       
}

renderHeatmapCalendar(this.container, calendarData)

```

```dataviewjs
dv.span("**🪙 경제용어2개 **")

const calendarData = {
    colors: {
        red: ["#ff9e82","#ff7b55","#ff4d1a","#e73400","#bd2a00",]
    },
    entries: []
}

for(let page of dv.pages('"obsidian_repo/Planner/Daily"').where(p=>p.경제용어2개)){
    calendarData.entries.push({
        date: page.file.name,
        intensity: page.경제용어2개,
        content: await dv.span(`[](${page.file.name})`), //for hover preview
    })
       
}

renderHeatmapCalendar(this.container, calendarData)

```
```dataviewjs
dv.span("**📝 수학정리2개 **")

const calendarData = {
    colors: {
        red: ["#ff9e82","#ff7b55","#ff4d1a","#e73400","#bd2a00",]
    },
    entries: []
}

for(let page of dv.pages('"obsidian_repo/Planner/Daily"').where(p=>p.수학정리2개)){
    calendarData.entries.push({
        date: page.file.name,
        intensity: page.수학정리2개,
        content: await dv.span(`[](${page.file.name})`), //for hover preview
    })
       
}

renderHeatmapCalendar(this.container, calendarData)

```
```dataviewjs
dv.span("**❣️ 감사노트 **")

const calendarData = {
    colors: {
        red: ["#ff9e82","#ff7b55","#ff4d1a","#e73400","#bd2a00",]
    },
    entries: []
}

for(let page of dv.pages('"obsidian_repo/Planner/Daily"').where(p=>p.감사노트)){
    calendarData.entries.push({
        date: page.file.name,
        intensity: page.감사노트,
        content: await dv.span(`[](${page.file.name})`), //for hover preview
    })
       
}

renderHeatmapCalendar(this.container, calendarData)

```
