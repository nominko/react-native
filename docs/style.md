---
id: style
title: Style
---

React Native-д хэв маягийг тодорхойлоход ямар нэг онцгой хэл, синтакс шаардлагагүй. Ердөө Javascript ашиглан аппликейшныхаа хэв загварыг гаргана. Бүх гол компонент нь `style` нэртэй пропыг зөвшөөрдөг. 
Хэв маягийн нэр өнгө нь [values](colors.md) веб дээр CSS хэрхэн ажилладагтай адилхан.  Гэхдээ `background-color` гэхийн оронд `backgroundColor` гэх мэт үгийн дунд томоор бичсэн нэрэнд хамаарахгүй.  

`style` нэртэй проп нь цулгуй, хуучны Javascript байж болно. Энэ нь хамгийн энгийн бөгөөд бид ихэвчлэн жишиг код болгон ашигладаг. Мөн та хэв маягийн массив ашиглаж болно. Массивийн сүүлийн хэв маяг нь тэргүүнд гарч ирдэг. Өмнө нь ашигласан хэв маягаа дахин ашиглах болон энэ функцийг ашиглах боломжтой. 

Компонент нь илүү төвөгтэй болж ирдэг учир нэг газар хэд хэдэн хэв маягийг тодорхойлох бол `StyleSheet.create`-ийг ашиглавал илүү цэвэрхэн байдаг. Жишээ нь:  

```ReactNativeWebPlayer
import React, { Component } from 'react';
import { AppRegistry, StyleSheet, Text, View } from 'react-native';

const styles = StyleSheet.create({
  bigBlue: {
    color: 'blue',
    fontWeight: 'bold',
    fontSize: 30,
  },
  red: {
    color: 'red',
  },
});

export default class LotsOfStyles extends Component {
  render() {
    return (
      <View>
        <Text style={styles.red}>just red</Text>
        <Text style={styles.bigBlue}>just bigBlue</Text>
        <Text style={[styles.bigBlue, styles.red]}>bigBlue, then red</Text>
        <Text style={[styles.red, styles.bigBlue]}>red, then bigBlue</Text>
      </View>
    );
  }
}

// skip this line if using Create React Native App
AppRegistry.registerComponent('AwesomeProject', () => LotsOfStyles);
```
Компонентүүээ `style` пропыг хүлээн зөвшөөрдөг болгочихвол эргээд дэд компонентүүдийнхаа хэв маягийг гаргахад ашиглаж болно. Мөн үүнийг CSS доторх шиг "cascade" маягтай болгоход ашиглаж олно.

Текстийн хэв маягийг өөрчлөлх олон янзын арга бий. [Text component reference](text.md) гэсэн рүү орж бүрэн жагсаалтыг харна уу.

Одоо та текстийг хэрхэн гоёмсог болгох тухай мэдсэн тул дараа нь 
 [Компонентын хэмжийг хэрхэн удирдах](height-and-width.md) тухай мэдээлэлтэй танилцана уу.
