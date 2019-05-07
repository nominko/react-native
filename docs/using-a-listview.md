---
id: using-a-listview
Гарчиг: List Views ашиглах
---

React Native-т жагсаалт бүхий өгөгдөлд зориулсан багц компонент байдаг. Ерөнхийдөө та [FlatList](flatlist.md) эсвэл [SectionList](sectionlist.md) ашиглах хэрэгтэй болно. 

`FlatList` компонент нь өөрчлөлт орох жагсаалтыг гүйлгэдэг компонент юм. Зарим зүйлст өөрчлөлт орох, урт жагсаалт байгаа үед `FlatList` ашиглах нь  тохиромжтой. Илүү ерөнхий [`ScrollView`](using-a-scrollview.md)-ийг бодвол`FlatList` нь бүх элементүүдийг биш одоо дэлгэц дээр харагдаж байгаа зүйлсийг л ажиллуулдаг.

`FlatList` компонентэд `data` болон `renderItem` гэсэн хоёр пропс шаардлагатай. `data` нь жагсаалтын мэдээллийн эх сурвалж нь юм. `renderItem` нь уг эх сурвалжаас нэг зүйлийг аваад форматтай компонент дээр ирж ажиллуулдаг. 

Энэ жишээ дээр тогтсон өгөгдлийн энгийн `FlatList` хэрхэн үүсгэхийг харуулж байна. `data` пропс доторх зүйл бүхэн `Text` компонент шиг ажиллаж байна. 


```SnackPlayer name=FlatList%20Basics
import React, { Component } from 'react';
import { AppRegistry, FlatList, StyleSheet, Text, View } from 'react-native';

export default class FlatListBasics extends Component {
  render() {
    return (
      <View style={styles.container}>
        <FlatList
          data={[
            {key: 'Devin'},
            {key: 'Jackson'},
            {key: 'James'},
            {key: 'Joel'},
            {key: 'John'},
            {key: 'Jillian'},
            {key: 'Jimmy'},
            {key: 'Julie'},
          ]}
          renderItem={({item}) => <Text style={styles.item}>{item.key}</Text>}
        />
      </View>
    );
  }
}

const styles = StyleSheet.create({
  container: {
   flex: 1,
   paddingTop: 22
  },
  item: {
    padding: 10,
    fontSize: 18,
    height: 44,
  },
})

// skip this line if using Create React Native App
AppRegistry.registerComponent('AwesomeProject', () => FlatListBasics);
```

Хэрэв та iOS дээрх `UITableView` шиг бүлэг өгөгдлийг хэсэгчлэн, магадгүй толгой хэсэгтэй оруулахыг хүсэж байгаа бол [SectionList](sectionlist.md) ашиглаарай. 


```SnackPlayer name=SectionList%20Basics
import React, { Component } from 'react';
import { AppRegistry, SectionList, StyleSheet, Text, View } from 'react-native';

export default class SectionListBasics extends Component {
  render() {
    return (
      <View style={styles.container}>
        <SectionList
          sections={[
            {title: 'D', data: ['Devin']},
            {title: 'J', data: ['Jackson', 'James', 'Jillian', 'Jimmy', 'Joel', 'John', 'Julie']},
          ]}
          renderItem={({item}) => <Text style={styles.item}>{item}</Text>}
          renderSectionHeader={({section}) => <Text style={styles.sectionHeader}>{section.title}</Text>}
          keyExtractor={(item, index) => index}
        />
      </View>
    );
  }
}

const styles = StyleSheet.create({
  container: {
   flex: 1,
   paddingTop: 22
  },
  sectionHeader: {
    paddingTop: 2,
    paddingLeft: 10,
    paddingRight: 10,
    paddingBottom: 2,
    fontSize: 14,
    fontWeight: 'bold',
    backgroundColor: 'rgba(247,247,247,1.0)',
  },
  item: {
    padding: 10,
    fontSize: 18,
    height: 44,
  },
})

// skip this line if using Create React Native App
AppRegistry.registerComponent('AwesomeProject', () => SectionListBasics);
```

Жагсаалт харах функцийн түгээмэл ашиглагддаг нэг хэлбэр нь серверээс татсан датагаа харуулах юм. Ингэхийн тулд та 
[React Native доторх сүлжээний тухай ](network.md) мэддэг байх хэрэгтэй.
