---
id: using-a-scrollview
Гарчиг: ScrollView ашиглах
---

[ScrollView](scrollview.md) гэдэг нь олон тооны компонент, харагдацыг байрлуулах scroll хийх зүйлсийг агуулдаг зүйл юм.
Гүйлгэж харах зүйлс нь нэг төрлийн байх хэрэгтэй ба босоо болон хөндлөнгөөр гүйлгэх боломжтой (`horizontal` гэж тохируулснаар).

Энэхүү жишээнд босоо `ScrollView` -ийг зураг болон текс хослуулан хэрхэн хийх тухай харуулж байна.

```ReactNativeWebPlayer
import React, { Component } from 'react';
import { AppRegistry, ScrollView, Image, Text } from 'react-native';

export default class IScrolledDownAndWhatHappenedNextShockedMe extends Component {
  render() {
      return (
        <ScrollView>
          <Text style={{fontSize:96}}>Scroll me plz</Text>
          <Image source={{uri: "https://facebook.github.io/react-native/img/favicon.png", width: 64, height: 64}} />
          <Image source={{uri: "https://facebook.github.io/react-native/img/favicon.png", width: 64, height: 64}} />
          <Image source={{uri: "https://facebook.github.io/react-native/img/favicon.png", width: 64, height: 64}} />
          <Image source={{uri: "https://facebook.github.io/react-native/img/favicon.png", width: 64, height: 64}} />
          <Image source={{uri: "https://facebook.github.io/react-native/img/favicon.png", width: 64, height: 64}} />
          <Text style={{fontSize:96}}>If you like</Text>
          <Image source={{uri: "https://facebook.github.io/react-native/img/favicon.png", width: 64, height: 64}} />
          <Image source={{uri: "https://facebook.github.io/react-native/img/favicon.png", width: 64, height: 64}} />
          <Image source={{uri: "https://facebook.github.io/react-native/img/favicon.png", width: 64, height: 64}} />
          <Image source={{uri: "https://facebook.github.io/react-native/img/favicon.png", width: 64, height: 64}} />
          <Image source={{uri: "https://facebook.github.io/react-native/img/favicon.png", width: 64, height: 64}} />
          <Text style={{fontSize:96}}>Scrolling down</Text>
          <Image source={{uri: "https://facebook.github.io/react-native/img/favicon.png", width: 64, height: 64}} />
          <Image source={{uri: "https://facebook.github.io/react-native/img/favicon.png", width: 64, height: 64}} />
          <Image source={{uri: "https://facebook.github.io/react-native/img/favicon.png", width: 64, height: 64}} />
          <Image source={{uri: "https://facebook.github.io/react-native/img/favicon.png", width: 64, height: 64}} />
          <Image source={{uri: "https://facebook.github.io/react-native/img/favicon.png", width: 64, height: 64}} />
          <Text style={{fontSize:96}}>What's the best</Text>
          <Image source={{uri: "https://facebook.github.io/react-native/img/favicon.png", width: 64, height: 64}} />
          <Image source={{uri: "https://facebook.github.io/react-native/img/favicon.png", width: 64, height: 64}} />
          <Image source={{uri: "https://facebook.github.io/react-native/img/favicon.png", width: 64, height: 64}} />
          <Image source={{uri: "https://facebook.github.io/react-native/img/favicon.png", width: 64, height: 64}} />
          <Image source={{uri: "https://facebook.github.io/react-native/img/favicon.png", width: 64, height: 64}} />
          <Text style={{fontSize:96}}>Framework around?</Text>
          <Image source={{uri: "https://facebook.github.io/react-native/img/favicon.png", width: 64, height: 64}} />
          <Image source={{uri: "https://facebook.github.io/react-native/img/favicon.png", width: 64, height: 64}} />
          <Image source={{uri: "https://facebook.github.io/react-native/img/favicon.png", width: 64, height: 64}} />
          <Image source={{uri: "https://facebook.github.io/react-native/img/favicon.png", width: 64, height: 64}} />
          <Image source={{uri: "https://facebook.github.io/react-native/img/favicon.png", width: 64, height: 64}} />
          <Text style={{fontSize:80}}>React Native</Text>
        </ScrollView>
    );
  }
}

// skip these lines if using Create React Native App
AppRegistry.registerComponent(
  'AwesomeProject',
  () => IScrolledDownAndWhatHappenedNextShockedMe);
```

ScrollViews-т `pagingEnabled` пропс ашиглан эргүүлэх үйлдлийн тусламжтайгаар хуудсуудыг эргүүлэн хардаг болдог тохиргоо хийж болно. Android дээр [ViewPagerAndroid](viewpagerandroid.md) компонентийг ашиглан харагдах байдлыг хөндлөнгөөр нь эргүүлдэг болгож болно.

iOS  дээр нэг зүйл агуулсан ScrollView-тай үед хэрэглэгчийг тухайн контентийг томруулж харах боломжтой. 
`maximumZoomScale` болон `minimumZoomScale` пропсийн тохиргоо хийх бөгөөд хэрэглэгч тань томруулж, багасгахын тулд чимхэх, тэлэх үйлдлийг хуруугаараа хийнэ. 

Жэмжээ багатай жижиг зүйлсийг харуулах үед ScrollView их үр дүнтэй байдаг. `ScrollView`-ийн бүх элемент, харагдац нь дэлгэц дээр харагдахгүй байсан ч ажиллаж байдаг. 

Хэрэв та дэлгэцэд багтахаар олон зүйлс бүхий жагсаалт харуулахыг хүсэж байгаа бол `FlatList` ашиглаарай. Одоо харин [жагсаалт харах тухай ](using-a-listview.md) үзэцгээе. 
