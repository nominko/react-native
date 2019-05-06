---
id: handling-touches
Гарчиг: Дэлгэцэд хүрэхийг зохицуулах
---

Хэрэглэгчид гар утасны апптай харилцахдаа дэлгэцэд хүрдэг. Товчлуур дээр дарах, жагсаалт гүйлгэх, газрын зураг томруулах гэх мэт үйлдлүүд хийдэг.  React Native-т бүх төрлийн үйлдлийг зохицуулдаг компонент байдаг. Мөн[хариу үйлдлийн систем](gesture-responder-system.md) цогц байдаг бөгөөд энэ нь үйлдлийг илүү ахисан түвшинд таних юм. Гэхдээ таны сонирхлыг татах нэг компонент татах нэг гол компонент бол энгийн Товч юм. 

## Энгийн товчийг харуулах

[Товч](button.md) нь бүх платформ дээр сайхан харагдах энгийн товчин компонент юм. Элдэв маяггүй товч нэг иймэрхүү харагдана:

```javascript
<Button
  onPress={() => {
    Alert.alert('You tapped the button!');
  }}
  title="Press Me"
/>
```

Энэ товч нь iOS дээр цэнхэр тэмдэг харагдах бол Android дээр цагаан тексттэй дугуй ирмэгтэй цэнхэр тэгш өнцөгт харагдана. Энэ товчийг дарвал "onPress" ажиллах бөгөөд анхааруулга цонх дэлгэц дээр гарч ирнэ. Хэрэв хүсвэл та "өнгийн" пропыг тохируулж товчныхоо өнгийг өөрчилж болно. 

![](/react-native/docs/assets/Button.png)

Доорх жишээг ашиглан `Товч` компонентийг хүссэнээрээ ашиглаад үзээрэй. Баруун доод хэсэгт байрлах солих товч дээр дараад аппаа ямар платформ дээр урьдчилан үзэхээ сонгож болно. Тэгээд "Tap to Play" гэсэн дээр дарж аппаа урьдчилан харна.

```SnackPlayer name=Button%20Basics
import React, { Component } from 'react';
import { Alert, AppRegistry, Button, StyleSheet, View } from 'react-native';

export default class ButtonBasics extends Component {
  _onPressButton() {
    Alert.alert('You tapped the button!')
  }

  render() {
    return (
      <View style={styles.container}>
        <View style={styles.buttonContainer}>
          <Button
            onPress={this._onPressButton}
            title="Press Me"
          />
        </View>
        <View style={styles.buttonContainer}>
          <Button
            onPress={this._onPressButton}
            title="Press Me"
            color="#841584"
          />
        </View>
        <View style={styles.alternativeLayoutButtonContainer}>
          <Button
            onPress={this._onPressButton}
            title="This looks great!"
          />
          <Button
            onPress={this._onPressButton}
            title="OK!"
            color="#841584"
          />
        </View>
      </View>
    );
  }
}

const styles = StyleSheet.create({
  container: {
   flex: 1,
   justifyContent: 'center',
  },
  buttonContainer: {
    margin: 20
  },
  alternativeLayoutButtonContainer: {
    margin: 20,
    flexDirection: 'row',
    justifyContent: 'space-between'
  }
});

// skip this line if using Create React Native App
AppRegistry.registerComponent('AwesomeProject', () => ButtonBasics);
```

## Touchables

Хэрвээ энгийн товч нь таны апп-д тохирохгүй бол та React Native-ийн "Touchable" компонентийг ашиглан өөрийн гэсэн товчоо бүтээх боломжтой. "Touchable" компонент нь товших үйлдлийг таних чадвартай бөгөөд үйлдлийг таньсан даруйдаа хариу үйлдлийг дэлгэц дээр харуулдаг. Эдгээр компонентэд өгөгдмөл хэв маяг гэж байхгүй. Апп дээрээ гоё харагдуулахын тулд бага зэрэг хөдөлмөрлөх шаардлагатай.
Аль "Touchable" компонент ашиглах нь ямар төрлийн хариу үйлдэл үзүүлэхийг хүсэж байгаагаас тань хамаарна. 

- Ерөнхийдөө, та [**TouchableHighlight**](touchablehighlight.md)-ыг товч эсвэл вебийн холбоос ашиглахыг хүссэн газартаа ашиглаж болно. Товч дээр дарах үед арын суурь өгнө бараан болно. 

- Android дээр хэрэглэгч хүрэх үед бэхний өнгө хөвөрдөг хариу үйлдэл хийдэг болгохыг хүсвэл [**TouchableNativeFeedback**](touchablenativefeedback.md) ашиглаарай. 

- [**TouchableOpacity**](touchableopacity.md)гэдгийг ашиглавал товчны харагдах хүч сулрах бөгөөд хэрэглэгч дэлгэц дээр дарж байх үед арын суурийг нэвт харагддаг болгоно. 

- Хэрэв та товших үйлдлийг хүлээн авах ч ямар нэг хариу үйлдэл дэлгэц дээр харуулахгүй байхыг хүсвэл [**TouchableWithoutFeedback**](touchablewithoutfeedback.md) ашиглаарай.

Зарим үед хэрэглэгч нэг зүйл дээр дараад, хэр удаан харж буйг та мэдэхийг хүсэж магад. "Touchable" компонентуудын аль ч `onLongPress` пропсийг ажиллуулан энэхүү удаан дарах явцыг зохицуулж болно.

Бодитоор ямар байдгийг харцгаая:

```SnackPlayer platform=android&name=Touchables
import React, { Component } from 'react';
import { Alert, AppRegistry, Platform, StyleSheet, Text, TouchableHighlight, TouchableOpacity, TouchableNativeFeedback, TouchableWithoutFeedback, View } from 'react-native';

export default class Touchables extends Component {
  _onPressButton() {
    Alert.alert('You tapped the button!')
  }

  _onLongPressButton() {
    Alert.alert('You long-pressed the button!')
  }


  render() {
    return (
      <View style={styles.container}>
        <TouchableHighlight onPress={this._onPressButton} underlayColor="white">
          <View style={styles.button}>
            <Text style={styles.buttonText}>TouchableHighlight</Text>
          </View>
        </TouchableHighlight>
        <TouchableOpacity onPress={this._onPressButton}>
          <View style={styles.button}>
            <Text style={styles.buttonText}>TouchableOpacity</Text>
          </View>
        </TouchableOpacity>
        <TouchableNativeFeedback
            onPress={this._onPressButton}
            background={Platform.OS === 'android' ? TouchableNativeFeedback.SelectableBackground() : ''}>
          <View style={styles.button}>
            <Text style={styles.buttonText}>TouchableNativeFeedback</Text>
          </View>
        </TouchableNativeFeedback>
        <TouchableWithoutFeedback
            onPress={this._onPressButton}
            >
          <View style={styles.button}>
            <Text style={styles.buttonText}>TouchableWithoutFeedback</Text>
          </View>
        </TouchableWithoutFeedback>
        <TouchableHighlight onPress={this._onPressButton} onLongPress={this._onLongPressButton} underlayColor="white">
          <View style={styles.button}>
            <Text style={styles.buttonText}>Touchable with Long Press</Text>
          </View>
        </TouchableHighlight>
      </View>
    );
  }
}

const styles = StyleSheet.create({
  container: {
    paddingTop: 60,
    alignItems: 'center'
  },
  button: {
    marginBottom: 30,
    width: 260,
    alignItems: 'center',
    backgroundColor: '#2196F3'
  },
  buttonText: {
    padding: 20,
    color: 'white'
  }
});

// Skip this line if you are using Create React Native App
AppRegistry.registerComponent('AwesomeProject', () => Touchables);
```

## Жагсаалт гүйлгэх, хуудас эргүүлэх, and томруулах

Гар утасны апп дээр түгээмэл хийгддэг өөр нэг үйлдэл нь гүйлгэх эсвэл хөндлөн, босоо байрлалд шилжих юм. Ингэснээр хэрэглэгч жагсаасан зүйлсийг гүйлгэн харж, хуудас бүхий контентийг гүйлгэн харах боломжтой. Эдгээр болон бусад үйлдлийн талаар мэдэхийг хүсвэл  [ScrollView хэрхэн ашиглах тухай](using-a-scrollview.md) уншаарай.
