# Lists, Maintenance, Navigation

### Lists
- list를 일반적인 형태가 아닌 Grid 형식으로 보여주고 싶을 때가 있음 => `GridView` 사용
- `GridView.count`를 통해 만들고 싶은 그리드뷰의 행, 열을 조정할 수 있음
  - `crossAxisCount` : 화면에 표현할 열을 설정 (2로 설정 시, 2열로 보임)
  - `crossAxisSpacing` : 횡(세로)축 간격 설정
  - 'mainAxisSpacing' : 주(가로)축 간격 설정
- `ListView` - 수평 리스트 표시 시 사용
  - `scrollDirection` : 기본은 수직 리스트 (Axis.vertical/Axis.horizontal)
- `ListTile` : 리스트 뷰의 아이템
  - `leading` : 타이틀 전에 표시 되는 위젯. 일반적으로 Icon/ CircleAvatar
  ```
  ListTile(title: Text('Item #$index'),
           leading: CircleAvatar(backgroundColor: Colors.brown.shade800,
                        child: Text('A')))
  ```

#### 다른 타입의 아이템들을 리스트 표시 시 방법
1. 다른 타입의 아이템들을 데이터 소스로 생성
2. 데이터 소스를 위젯으로 변경

#### FloatingAppBar List
- 사용자 스크롤 다운 시 Appbar가 사라지는 형태

### Maintenance

### Navigation
- `Navigator`
  - push : 스택에 화면 추가
  - pop : 이전 화면으로 돌아감
  - `routes`
    - 네비게이터로 정의되면 있는 프로퍼티
    - 각 위젯 별로 이름 지정 시 해당 화면으로 이동 가능
    - home, / 는 같이 사용할 수 없음
    - `initialRoute` : 최초로 보여줄 라우팅 화면을 정할 수 있음
    - 지정되지 않은 이름으로 pushedName 호출 시 `onGeneratedRoute`가 호출 -> 해당 메서드에서 반환되는 위젯으로 이동
