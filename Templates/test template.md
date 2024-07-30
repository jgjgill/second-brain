### 노트 생성 날짜
2024-07-30 18:57

### 노트 제목
test template

### 노트 저장 폴더

### 노트의 PC 경로
/Users/ijong-gil/Documents/Obsidian Vault/test template.md


### tp_date
<%tp.date.now("YYYY-MM-DD")%>
<%tp.date.tomorrow("YYYY-MM-DD")%>
<%tp.date.yesterday("YYYY-MM-DD")%>
<%tp.date.weekday("YYYY-MM-DD", 0)%>

### tp_system

#### 클립 보드
<%tp.system.clipboard()%>

#### 드롭다운 메뉴
<%tp.system.suggester(
[1, 2, 3, 4, 5],
["가","나","다","라","마"]
)%>

#### 텍스트 필드
<%tp.system.prompt("오늘의 기분은?", "")%>