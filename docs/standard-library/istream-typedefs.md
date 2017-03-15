---
title: "&lt;istream&gt; 형식 정의 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 55bc1f84-53a7-46ca-a36f-ac6ef75d0374
caps.latest.revision: 10
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: e3607735f989b61f373eb689b8fe3b2dee656f7b
ms.lasthandoff: 02/24/2017

---
# <a name="ltistreamgt-typedefs"></a>&lt;istream&gt; 형식 정의
||||  
|-|-|-|  
|[iostream](#iostream)|[istream](#istream)|[wiostream](#wiostream)|  
|[wistream](#wistream)|  
  
##  <a name="a-nameiostreama--iostream"></a><a name="iostream"></a>  iostream  
 `char`에서 특수화된 `basic_iostream` 형식입니다.  
  
```  
typedef basic_iostream<char, char_traits<char>> iostream;  
```  
  
### <a name="remarks"></a>설명  
 이 형식은 기본 문자 특성을 포함하는 `char` 형식의 요소용으로 특수화된 [basic_iostream](../standard-library/basic-iostream-class.md) 템플릿 클래스의 동의어입니다.  
  
##  <a name="a-nameistreama--istream"></a><a name="istream"></a>  istream  
 `char`에서 특수화된 `basic_istream` 형식입니다.  
  
```  
typedef basic_istream<char, char_traits<char>> istream;  
```  
  
### <a name="remarks"></a>설명  
 이 형식은 기본 문자 특성을 포함하는 `char` 형식의 요소용으로 특수화된 [basic_istream](../standard-library/basic-istream-class.md) 템플릿 클래스의 동의어입니다.  
  
##  <a name="a-namewiostreama--wiostream"></a><a name="wiostream"></a>  wiostream  
 `wchar_t`에서 특수화된 `basic_iostream` 형식입니다.  
  
```  
typedef basic_iostream<wchar_t, char_traits<wchar_t>> wiostream;  
```  
  
### <a name="remarks"></a>설명  
 이 형식은 기본 문자 특성을 포함하는 `wchar_t` 형식의 요소용으로 특수화된 [basic_iostream](../standard-library/basic-iostream-class.md) 템플릿 클래스의 동의어입니다.  
  
##  <a name="a-namewistreama--wistream"></a><a name="wistream"></a>  wistream  
 `wchar_t`에서 특수화된 `basic_istream` 형식입니다.  
  
```  
typedef basic_istream<wchar_t, char_traits<wchar_t>> wistream;  
```  
  
### <a name="remarks"></a>설명  
 이 형식은 기본 문자 특성을 포함하는 `wchar_t` 형식의 요소용으로 특수화된 [basic_istream](../standard-library/basic-istream-class.md) 템플릿 클래스의 동의어입니다.  
  
## <a name="see-also"></a>참고 항목  
 [\<istream>](../standard-library/istream.md)


