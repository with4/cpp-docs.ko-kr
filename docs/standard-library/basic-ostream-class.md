---
title: "basic_ostream 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::basic_ostream"
  - "std.basic_ostream"
  - "ostream/std::basic_ostream"
  - "basic_ostream"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "basic_ostream 클래스"
ms.assetid: 5baadc65-b662-4fab-8c9f-94457c58cda1
caps.latest.revision: 24
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# basic_ostream 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 템플릿 클래스는 문자 특성이 **Tr**\([traits\_type](../Topic/basic_ios::traits_type.md)이라고도 함\)에 의해 결정되는 **Elem**\([char\_type](../Topic/basic_ios::char_type.md)이라고도 함\) 형식의 요소가 있는 스트림 버퍼에 요소 및 인코드된 개체의 삽입을 제어하는 개체를 설명합니다.  
  
## 구문  
  
```  
  
template <class   
_Elem  
, class   
_Tr  
 = char  
_  
traits<Elem> >  
   class basic  
_  
ostream  
       : virtual public basic  
_  
ios<  
_Elem  
,   
_Tr  
>  
  
```  
  
#### 매개 변수  
 `_Elem`  
 `char_type`  
  
 `_Tr`  
 문자 `traits_type`입니다.  
  
## 설명  
 [operator\<\<](../Topic/basic_ostream::operator%3C%3C.md)를 오버로드하는 대부분의 멤버 함수는 형식이 지정된 출력 함수입니다. 다음 패턴을 따릅니다.  
  
```  
iostate state = goodbit;  
const sentry ok( *this );  
if ( ok )  
   {try  
      {<convert and insert elements  
      accumulate flags in state> }  
   catch ( ... )  
      {try  
        {setstate( badbit ); }  
      catch ( ... )  
        {}  
      if ( ( exceptions( ) & badbit ) != 0 )  
        throw; }}  
width( 0 );    // Except for operator<<(Elem)  
setstate( state );  
return ( *this );  
```  
  
 다른 두 멤버 함수는 형식이 지정되지 않은 출력 함수입니다. 다음 패턴을 따릅니다.  
  
```  
iostate state = goodbit;  
const sentry ok( *this );  
if ( !ok )  
   state |= badbit;  
else  
   {try  
      {<obtain and insert elements  
      accumulate flags in state> }  
   catch ( ... )  
      {try  
         {setstate( badbit ); }  
      catch ( ... )  
         {}  
      if ( ( exceptions( ) & badbit ) != 0 )  
         throw; }}  
setstate( state );  
return ( *this );  
```  
  
 두 함수 그룹은 요소를 삽입하는 동안 오류가 발생하는 경우 [setstate](../Topic/basic_ios::setstate.md)**\(badbit\)**를 호출합니다.  
  
 basic\_istream\<**Elem**, **Tr**\> 클래스의 개체는 [basic\_ios](../standard-library/basic-ios-class.md)**\<Elem**, **Tr\>** 클래스의 가상 공용 기준 개체만 저장합니다.  
  
## 예제  
 예를 참조 [basic\_ofstream 클래스](../standard-library/basic-ofstream-class.md) 출력 스트림에 대 한 자세한 내용을 보려면 합니다.  
  
### 생성자  
  
|||  
|-|-|  
|[basic\_ostream](../Topic/basic_ostream::basic_ostream.md)|`basic_ostream` 개체를 생성합니다.|  
  
### 멤버 함수  
  
|||  
|-|-|  
|[flush](../Topic/basic_ostream::flush.md)|버퍼를 플러시합니다.|  
|[put](../Topic/basic_ostream::put.md)|스트림에 문자를 넣습니다.|  
|[seekp](../Topic/basic_ostream::seekp.md)|출력 스트림 내의 위치를 다시 설정합니다.|  
|[sentry](../Topic/basic_ostream::sentry.md)|중첩 클래스는 선언에서 형식이 지정된 출력 함수 및 형식이 지정되지 않은 출력 함수를 구성하는 개체를 설명합니다.|  
|[swap](../Topic/basic_ostream::operator=.md)|이 `basic_ostream` 개체의 값을 제공된 `basic_ostream` 개체의 값으로 교환합니다.|  
|[tellp](../Topic/basic_ostream::tellp.md)|출력 스트림 내의 위치를 보고합니다.|  
|[쓰기](../Topic/basic_ostream::write.md)|스트림에 문자를 넣습니다.|  
  
### 연산자  
  
|||  
|-|-|  
|[operator\=](../Topic/basic_ostream::operator=.md)|제공된 `basic_ostream` 개체 매개 변수의 값을 이 개체에 할당합니다.|  
|[operator\<\<](../Topic/basic_ostream::operator%3C%3C.md)|스트림에 씁니다.|  
  
## 요구 사항  
 **헤더:** \<ostream\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream 프로그래밍](../standard-library/iostream-programming.md)   
 [iostreams 규칙](../standard-library/iostreams-conventions.md)