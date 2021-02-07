# Gestures, Images
### InkWell

- 탭 시도시, ripple animation(번지는 효과)을 가능하게 해주는 위젯

### GestureDetector

- 탭, 드래그 등의 제스처가 있을 때, 사용자에게 응답을 돌려줄 수 있음
- onTap 콜백에 필요 내역을 작성

### Swipe to dismiss

- 모바일에서 많이 쓰이는 패턴
- `Dismissible` 위젯을 통해 해당 패턴을 만들 수 있음
    - `background` 를 제공하면, Swipe 될 때 해당 배경색 표시

```dart
Dismissible(
  // Show a red background as the item is swiped away.
  background: Container(color: Colors.red),
  key: Key(item),
  onDismissed: (direction) {
    setState(() {
      items.removeAt(index);
    });

    Scaffold
        .of(context)
        .showSnackBar(SnackBar(content: Text("$item dismissed")));
  },
  child: ListTile(title: Text('$item')),
);
```

---

## Images

### 인터넷 이미지 노출

- `Image` 위젯을 통해 이미지를 다룰 수 있음
- `Image.network(url)` 을 통해 인터넷 상의 이미지 표시 가능

### Fade Image

- `FadeInImage` 위젯을 통해 이미지가 로드 되기 전에 디폴트 이미지를 설정 할 수 있음
- 로컬 에셋에 있는 것을 이용하거나 패키지 상에 있는 이미지를 placeholder로 이용할 수 있음

```dart
FadeInImage.memoryNetwork(
  placeholder: kTransparentImage,
  image: 'https://picsum.photos/250?image=9',
);
```

### 이미지 캐싱

- 웹에서 이미지를 캐싱하여 오프라인으로 사용할 수 있음
- `CachedNetworkImage` 가 해당 기능을 제공
- FadeInImage와 마찬가지로 이미지 placeholder를 제공해 spinner 등 설정 가능

```dart
CachedNetworkImage(
  placeholder: (context, url) => CircularProgressIndicator(),
  imageUrl: 'https://picsum.photos/250?image=9',
);
```