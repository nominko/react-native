---
id: network
Гарчиг: Сүлжээ
---

Ихэнх гар утасны аппууд мэдээллээ remote URL-аас татдаг. Танд REST API-д POST хүсэлт илгээх эсвэл өөр серверээс өөрчлөлтгүй контент татах хэрэг гарч магад.


## Fetch ашиглах

React Native-т сүлжээний хэрэгцээг тань хангах [Fetch API](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API) байдаг. Хэрэв та `XMLHttpRequest` эсвэл өөр сүлжээний API ашиглаж байсан бол Fetch танд илүү ойр санагдах байх. 
Та дэлгэрэнгүй мэдээлэл авах бол MDN-ийн [Fetch ашиглах тухай](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API/Using_Fetch) мэдээллийг уншаарай.

#### Хүсэлт гаргах

Хэрэв та дурын URL-ээс контент fetch хийх бол URL-ийг өгөхөд л хангалттай.

```javascript
fetch('https://mywebsite.com/mydata.json');
```

Fetch нь мөн HTTP хүсэлтийг хүссэнээрээ өөрчлөх боломж бүхий нэмэлт хоёрдогч хүсэлт үүсгэдэг. Та нэмж толгой хэсэг заах эсвэл POST хүсэлт илгээх бол:

```javascript
fetch('https://mywebsite.com/endpoint/', {
  method: 'POST',
  headers: {
    Accept: 'application/json',
    'Content-Type': 'application/json',
  },
  body: JSON.stringify({
    firstParam: 'yourValue',
    secondParam: 'yourOtherValue',
  }),
});
```

Бүрэн жагсаалтыг харах: [Fetch Request docs](https://developer.mozilla.org/en-US/docs/Web/API/Request) 

#### Хариул үйлдэл зохицуулах

Дээрх жишээнүүдэд хэрхэн хүсэлт хэрхэн гаргах тухай харуулсан. Ихэнх тохиолдолд та хариу үйлдэл ирэх үед ямар нэг үйлдэл хийх хэрэгтэй болно. 

Сүлжээний ажил нь угийн зэрэгцээ бус явагддаг. Fetch аргууд нь зэрэгцээ бус орчинд ажиллах код бичихийг хялбар болгох [Promise](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)-т хүргэдэг:

```javascript
function getMoviesFromApiAsync() {
  return fetch('https://facebook.github.io/react-native/movies.json')
    .then((response) => response.json())
    .then((responseJson) => {
      return responseJson.movies;
    })
    .catch((error) => {
      console.error(error);
    });
}
```

Мөн та React Native апп дотор санал болгосон ES2017 `async`/`await` синтаксийг ашиглах боломжтой:

```javascript
async function getMoviesFromApi() {
  try {
    let response = await fetch(
      'https://facebook.github.io/react-native/movies.json',
    );
    let responseJson = await response.json();
    return responseJson.movies;
  } catch (error) {
    console.error(error);
  }
}
```
`fetch` хийх үеэр гарсан алдааг барьж авахаа мартав аа. Эс бөгөөд чимээгүй орхигдох болно.

```SnackPlayer name=Fetch%20Example
import React from 'react';
import { FlatList, ActivityIndicator, Text, View  } from 'react-native';

export default class FetchExample extends React.Component {

  constructor(props){
    super(props);
    this.state ={ isLoading: true}
  }

  componentDidMount(){
    return fetch('https://facebook.github.io/react-native/movies.json')
      .then((response) => response.json())
      .then((responseJson) => {

        this.setState({
          isLoading: false,
          dataSource: responseJson.movies,
        }, function(){

        });

      })
      .catch((error) =>{
        console.error(error);
      });
  }



  render(){

    if(this.state.isLoading){
      return(
        <View style={{flex: 1, padding: 20}}>
          <ActivityIndicator/>
        </View>
      )
    }

    return(
      <View style={{flex: 1, paddingTop:20}}>
        <FlatList
          data={this.state.dataSource}
          renderItem={({item}) => <Text>{item.title}, {item.releaseYear}</Text>}
          keyExtractor={({id}, index) => id}
        />
      </View>
    );
  }
}
```

> SSL ашиглан кодлогдоогүй ямар ч хүсэлтийг iOS цаанаасаа блок хийх тохиргоотой байдаг. Хэрэв та ил текстэн URL (`http`-гээр эхэлсэн)-аас fetch хийх гэж байгаа бол эхлээд [Апп Зөөх Аюулгүй байдлын онцгой нэмэлт](integration-with-existing-apps.md#test-your-integration)нэмэх хэрэгтэй. Хэрэв та ямар домайнд хандахаа өмнө нь мэдэж байвал зөвхөн тэдгээр домайнд зориулан онцгой нэмэлтийг суурилуулбал илүү аюулгүй байх болно. Хэрэв бэлэн болох хүртэл домайнаа мэдэхгүй бол [ATS-ийг бүрэн идэвхгүй болгож болно](integration-with-existing-apps.md#app-transport-security). Гэхдээ 2017 оны нэгдүгээр сараас  [ATS-ыг идэвхгүй болгоход Apple's App Store review тодорхой шалтгаан хүсдэг болсон](https://forums.developer.apple.com/thread/48979)
Илүү мэдээлэл авахыг хүсвэл [Apple-ийн зааврыг (https://developer.apple.com/library/ios/documentation/General/Reference/InfoPlistKeyReference/Articles/CocoaKeys.html#//apple_ref/doc/uid/TP40009251-SW33) уншина уу. 

### Сүлжээний бусад сан ашиглах

[XMLHttpRequest API](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest) нь React Native-д хийгдсэн байдаг. Энэ нь та [frisbee](https://github.com/niftylettuce/frisbee), [axios](https://github.com/mzabriskie/axios) гэх мэт гуравдагч санг ашиглах, эсвэл хүсвэл XMLHttpRequest API шууд ашиглаж боломжтой. 

```javascript
var request = new XMLHttpRequest();
request.onreadystatechange = (e) => {
  if (request.readyState !== 4) {
    return;
  }

  if (request.status === 200) {
    console.log('success', request.responseText);
  } else {
    console.warn('error');
  }
};

request.open('GET', 'https://mywebsite.com/endpoint/');
request.send();
```

> Натив апп дотор вэб дээрх шиг [CORS](http://en.wikipedia.org/wiki/Cross-origin_resource_sharing)гэсэн зүйл байдаагүй учир XMLHttpRequest-д зориулсан аюулгүй модель нь өөр байдаг. 

## WebSocket дэмжих

React Native нь дан TCP (Дамжуулалт Хяналтын Протокол)-ээр хоёр зэрэгцээ холбооны суваг үүсгэдэг [WebSockets](https://developer.mozilla.org/en-US/docs/Web/API/WebSocket)-ийг дэмждэг. 

```javascript
var ws = new WebSocket('ws://host.com/path');

ws.onopen = () => {
  // connection opened
  ws.send('something'); // send a message
};

ws.onmessage = (e) => {
  // a message was received
  console.log(e.data);
};

ws.onerror = (e) => {
  // an error occurred
  console.log(e.message);
};

ws.onclose = (e) => {
  // connection closed
  console.log(e.code, e.reason);
};
```

## `fetch` болон cookie-дээр суурилсан баталгаажуулалттай холбоотой асуудлууд 

Доорх хоёр нь `fetch`-тэй одоогоор ажиллахгүй байгаа. 

- `redirect:manual`
- `credentials:omit`

* Android дээр толгойн хэсэг ижил нэртэй байвал зөвхөн сүүлийнх нь харагдана. Үүнтэй холбоотой түр зуурын шийдлийн тухай
эндээс уншаарай: https://github.com/facebook/react-native/issues/18837#issuecomment-398779994.
* Cookie дээр суурилсан баталгаажуулалт нь одоогоор тогтворгүй байгаа. Үүнтэй холбоотой үүссэн асуудлын талаар эндээс уншаарай: https://github.com/facebook/react-native/issues/23185
* iOS дээр `302` дагуу шууд чиглүүлж, `Set-Cookie` толгой харагдаж байвал cookie зөв тохиргоо хийгдээгүй байна гэсэн үг. Шууд чиглүүлэх процесс автоматаар болдог учир хүчингүй хугацаа дууссан горимоос болж шууд чиглүүлэх явц болсон бол хязгааргүй их хүсэлт бий болох боломжтой. 

