---
title: "istrstream 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- istrstream
- strstream/std::istrstream::rdbuf
- strstream/std::istrstream::str
dev_langs:
- C++
helpviewer_keywords:
- istrstream class
ms.assetid: c2d41c75-bd2c-4437-bd77-5939ce1b97af
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
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
ms.openlocfilehash: 528634e98da7f57ee915124d38f20277495efcdb
ms.contentlocale: ko-kr
ms.lasthandoff: 04/29/2017

---
# <a name="istrstream-class"></a>istrstream 클래스
[strstreambuf](../standard-library/strstreambuf-class.md) 클래스의 스트림 버퍼에서 요소 및 인코드된 개체의 추출을 제어하는 개체를 설명합니다.  
  
## <a name="syntax"></a>구문  
  
```
class istrstream : public istream
```  
  
## <a name="remarks"></a>설명  
 이 개체는 `strstreambuf` 클래스의 개체를 저장합니다.  
  
> [!NOTE]
>  이 클래스는 사용되지 않습니다. 대신 [istringstream](../standard-library/sstream-typedefs.md#istringstream) 또는 [wistringstream](../standard-library/sstream-typedefs.md#wistringstream)을 사용하는 것이 좋습니다.  
  
### <a name="constructors"></a>생성자  
  
|||  
|-|-|  
|[istrstream](#istrstream)|`istrstream` 형식의 개체를 생성합니다.|  
  
### <a name="member-functions"></a>멤버 함수  
  
|||  
|-|-|  
|[rdbuf](#rdbuf)|스트림의 연결된 `strstreambuf` 개체에 대한 포인터를 반환합니다.|  
|[str](#str)|[freeze](../standard-library/strstreambuf-class.md#freeze)를 호출한 다음 제어되는 시퀀스의 시작 부분에 대한 포인터를 반환합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<strstream >  
  
 **네임스페이스:** std  
  
##  <a name="istrstream"></a>  istrstream::istrstream  
 `istrstream` 형식의 개체를 생성합니다.  
  
```
explicit istrstream(
    const char* ptr);

explicit istrstream(
    char* ptr);

istrstream(
    const char* ptr,
    streamsize count);

istrstream(
    char* ptr,
    int count);
```  
  
### <a name="parameters"></a>매개 변수  
 `count`  
 버퍼의 길이입니다(`ptr`).  
  
 `ptr`  
 버퍼가 초기화되는 콘텐츠입니다.  
  
### <a name="remarks"></a>설명  
 모든 생성자는 [istream](../standard-library/istream-typedefs.md#istream)( **sb**)를 호출하여 기본 클래스를 초기화합니다. 여기서 **sb**는 [strstreambuf](../standard-library/strstreambuf-class.md) 클래스의 저장된 개체입니다. 처음 두 생성자도 `strstreambuf`( ( **const**`char` \*) `ptr`, 0 )을 호출하여 **sb**를 초기화합니다. 나머지 두 생성자는 대신 `strstreambuf`( ( **const**`char` *) `ptr`, `count` )를 호출합니다.  
  
##  <a name="rdbuf"></a>  istrstream::rdbuf  
 스트림의 연결된 strstreambuf 개체에 대한 포인터를 반환합니다.  
  
```
strstreambuf *rdbuf() const
```  
  
### <a name="return-value"></a>반환 값  
 스트림의 연결된 strstreambuf 개체에 대한 포인터입니다.  
  
### <a name="remarks"></a>설명  
 멤버 함수는 pointer 형식의 저장된 스트림 버퍼 주소를 [strstreambuf](../standard-library/strstreambuf-class.md)에 반환합니다.  
  
### <a name="example"></a>예제  
  `rdbuf`를 사용하는 샘플은 [strstreambuf::pcount](../standard-library/strstreambuf-class.md#pcount)를 참조하세요.  
  
##  <a name="str"></a>  istrstream::str  
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
 [istream](../standard-library/istream-typedefs.md#istream)   
 [C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream 프로그래밍](../standard-library/iostream-programming.md)   
 [iostreams 규칙](../standard-library/iostreams-conventions.md)




