---
id: handling-text-input
Гарчиг: Текст оруулах
---

[`Текст оруулах`](textinput.md#content) нь хэрэглэгчийг текст оруулах боломж олгодог үндсэн компонент юм.  Текстэнд өөрчлөлт орох бүрт дуудагддаг ажиллагаатай `onChangeText`  гэх проп, мөн текст оруулахад дуудагддаг `onSubmitEditing` гэх проптой.

Жишээ нь, хэрэглэгч үг бичиж байх үед та үгийг нь өөр хэл рүү орчуулж байлаа гэж бодъё. Шинээр орчуулж буй хувилбарт үг бүр нь ижил хэлбэрээр 🍕 бичигдэх болно. Тийм болохоор "Сайн уу, Боб" гэсэн өгүүлбэрийг "🍕🍕🍕" гэж орчуулагдана. 

```ReactNativeWebPlayer
import React, { Component } from 'react';
import { AppRegistry, Text, TextInput, View } from 'react-native';

export default class PizzaTranslator extends Component {
  constructor(props) {
    super(props);
    this.state = {text: ''};
  }

  render() {
    return (
      <View style={{padding: 10}}>
        <TextInput
          style={{height: 40}}
          placeholder="Type here to translate!"
          onChangeText={(text) => this.setState({text})}
        />
        <Text style={{padding: 10, fontSize: 42}}>
          {this.state.text.split(' ').map((word) => word && '🍕').join(' ')}
        </Text>
      </View>
    );
  }
}

// skip this line if using Create React Native App
AppRegistry.registerComponent('AwesomeProject', () => PizzaTranslator);
```

Өөрчлөлт орж байх учир энэ жишээнд`text`-ийг төлөвт  хадгалсан байгаа. 

Текст оруулахтай холбоотой өөр олон зүйлсийг та хийхийг хүсэж байгаа нь лавтай. Жишээ нь, хэрэглэгч бичиж байх үед та доторх текстийг баталж болно. Илүү дэлгэрэнгүй жишээг 
[Хяналттай компонентийн тухай React docs-той танилцаарай](https://reactjs.org/docs/forms.html#controlled-components), эсвэл [Текст оруулах тухай тайлбарыг сонирхоорой](textinput.md).

Текст оруулах нь хэрэглэгч апптай харилцаж байгаа нэг хэлбэр юм. Өөр нэг хэлбэр болох хэрэглэгч дэлгэцэд хүрэх харилцааг хэрхэн тохируулах тухай
 [эндээс уншаарай](handling-touches.md).
