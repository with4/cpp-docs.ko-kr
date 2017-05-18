---
title: "ostrstream 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ostrstream
- strstream/std::ostrstream::freeze
- strstream/std::ostrstream::pcount
- strstream/std::ostrstream::rdbuf
- strstream/std::ostrstream::str
dev_langs:
- C++
helpviewer_keywords:
- ostrstream class
ms.assetid: e2e34679-b266-4728-a8e1-8eda5d400e46
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: 2ed85552778f3bbf7346001e4dd4c858177ce49b
ms.contentlocale: ko-kr
ms.lasthandoff: 04/29/2017

---
# <a name="ostrstream-class"></a>ostrstream 클래스
[strstreambuf](../standard-library/strstreambuf-class.md) 클래스의 스트림 버퍼에 요소 및 인코드된 개체 삽입을 제어하는 개체를 설명합니다.  
  
## <a name="syntax"></a>구문  
  
```
class ostrstream : public ostream
```  
  
## <a name="remarks"></a>설명  
 이 개체는 `strstreambuf` 클래스의 개체를 저장합니다.  
  
> [!NOTE]
>  이 클래스는 사용되지 않습니다. 대신 [ostringstream](../standard-library/sstream-typedefs.md#ostringstream) 또는 [wostringstream](../standard-library/sstream-typedefs.md#wostringstream)을 사용하는 것이 좋습니다.  
  
### <a name="constructors"></a>생성자  
  
|||  
|-|-|  
|[ostrstream](#ostrstream)|`ostrstream` 형식의 개체를 생성합니다.|  
  
### <a name="member-functions"></a>멤버 함수  
  
|||  
|-|-|  
|[freeze](#freeze)|스트림 버퍼 작업을 통해 스트림 버퍼를 사용할 수 없게 합니다.|  
|[pcount](#pcount)|제어되는 시퀀스에 기록되는 요소 수의 개수를 반환합니다.|  
|[rdbuf](#rdbuf)|스트림의 연결된 `strstreambuf` 개체에 대한 포인터를 반환합니다.|  
|[str](#str)|[freeze](../standard-library/strstreambuf-class.md#freeze)를 호출한 다음 제어되는 시퀀스의 시작 부분에 대한 포인터를 반환합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<strstream >  
  
 **네임스페이스:** std  
  
##  <a name="freeze"></a>  ostrstream::freeze  
 스트림 버퍼 작업을 통해 스트림 버퍼를 사용할 수 없게 합니다.  
  
```
void freeze(bool _Freezeit = true);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Freezeit`  
 스트림을 고정할지를 나타내는 `bool`입니다.  
  
### <a name="remarks"></a>설명  
 구성원 함수는 [rdbuf](#rdbuf) -> [freeze](../standard-library/strstreambuf-class.md#freeze)(_ *Freezeit*)를 호출합니다.  
  
### <a name="example"></a>예제  
  **freeze**를 사용하는 예제는 [strstream::freeze](../standard-library/strstreambuf-class.md#freeze)를 참조하세요.  
  
##  <a name="ostrstream"></a>  ostrstream::ostrstream  
 `ostrstream` 형식의 개체를 생성합니다.  
  
```
ostrstream();

ostrstream(char* ptr,
    streamsize count,
    ios_base::openmode _Mode = ios_base::out);
```  
  
### <a name="parameters"></a>매개 변수  
 `ptr`  
 버퍼입니다.  
  
 `count`  
 버퍼의 크기(바이트)입니다.  
  
 `_Mode`  
 버퍼의 입력 및 출력 모드입니다. 자세한 내용은 [ios_base::openmode](../standard-library/ios-base-class.md#openmode)를 참조하세요.  
  
### <a name="remarks"></a>설명  
 두 생성자는 모두 [ostream](../standard-library/ostream-typedefs.md#ostream)( **sb**)를 호출하여 기본 클래스를 초기화합니다. 여기서 **sb**는 [strstreambuf](../standard-library/strstreambuf-class.md) 클래스의 저장된 개체입니다. 또한 첫 번째 생성자는 `strstreambuf`를 호출하여 **sb**를 초기화합니다. 두 번째 생성자는 다음의 두 가지 방법 중 하나로 기본 클래스를 초기화합니다.  
  
-   `_Mode` & **ios_base::app**== 0인 경우 `ptr`은 `count` 요소 배열의 첫 번째 요소를 지정해야 합니다. 그러면 생성자가 `strstreambuf`( `ptr`, `count`, `ptr`)를 호출합니다.  
  
-   그렇지 않은 경우 `ptr`은 첫 번째 요소가 `ptr`에 의해 지정되는 C 문자열이 포함된 count 요소 배열의 첫 번째 요소를 지정해야 합니다. 그러면 생성자가 `strstreambuf`( `ptr`, `count`, `ptr` + `strlen`( `ptr`) )를 호출합니다.  
  
##  <a name="pcount"></a>  ostrstream::pcount  
 제어되는 시퀀스에 기록되는 요소 수의 개수를 반환합니다.  
  
```
streamsize pcount() const;
```  
  
### <a name="return-value"></a>반환 값  
 제어되는 시퀀스에 기록되는 요소 수의 개수입니다.  
  
### <a name="remarks"></a>설명  
 구성원 함수는 [rdbuf](#rdbuf) -> [pcount](../standard-library/strstreambuf-class.md#pcount)를 반환합니다.  
  
### <a name="example"></a>예제  
  `pcount`를 사용하는 샘플은 [strstream::pcount](../standard-library/strstreambuf-class.md#pcount)를 참조하세요.  
  
##  <a name="rdbuf"></a>  ostrstream::rdbuf  
 스트림의 연결된 strstreambuf 개체에 대한 포인터를 반환합니다.  
  
```
strstreambuf *rdbuf() const
```  
  
### <a name="return-value"></a>반환 값  
 스트림의 연결된 strstreambuf 개체에 대한 포인터입니다.  
  
### <a name="remarks"></a>설명  
 구성원 함수는 **pointer** 형식의 저장된 스트림 버퍼 주소를 [strstreambuf](../standard-library/strstreambuf-class.md)에 반환합니다.  
  
### <a name="example"></a>예제  
  `rdbuf`를 사용하는 샘플은 [strstreambuf::pcount](../standard-library/strstreambuf-class.md#pcount)를 참조하세요.  
  
##  <a name="str"></a>  ostrstream::str  
 [freeze](../standard-library/strstreambuf-class.md#freeze)를 호출한 다음 제어되는 시퀀스의 시작 부분에 대한 포인터를 반환합니다.  
  
```
char *str();
```  
  
### <a name="return-value"></a>반환 값  
 제어되는 시퀀스의 시작 부분에 대한 포인터입니다.  
  
### <a name="remarks"></a>설명  
 구성원 함수는 [rdbuf](#rdbuf) -> [str](../standard-library/strstreambuf-class.md#str)을 반환합니다.  
  
### <a name="example"></a>예제  
  **str**을 사용하는 샘플은 [strstream::str](../standard-library/strstreambuf-class.md#str)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [ostream](../standard-library/ostream-typedefs.md#ostream)   
 [C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream 프로그래밍](../standard-library/iostream-programming.md)   
 [iostreams 규칙](../standard-library/iostreams-conventions.md)




