---
title: "&lt;sstream&gt; 형식 정의 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d102edd2-ecea-4a35-a398-cf96e58dd422
caps.latest.revision: 9
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 19af112017c3f6e9700a87f1d482fc4f319fb235
ms.lasthandoff: 02/24/2017

---
# <a name="ltsstreamgt-typedefs"></a>&lt;sstream&gt; 형식 정의
||||  
|-|-|-|  
|[istringstream](#istringstream)|[ostringstream](#ostringstream)|[stringbuf](#stringbuf)|  
|[stringstream](#stringstream)|[wistringstream](#wistringstream)|[wostringstream](#wostringstream)|  
|[wstringbuf](#wstringbuf)|[wstringstream](#wstringstream)|  
  
##  <a name="a-nameistringstreama--istringstream"></a><a name="istringstream"></a>  istringstream  
 `char` 템플릿 매개 변수에 대해 특수화된 `basic_istringstream` 형식을 만듭니다.  
  
```  
typedef basic_istringstream<char> istringstream;  
```  
  
### <a name="remarks"></a>설명  
 이 형식은 `char` 형식의 요소용으로 특수화된 [basic_istringstream](../standard-library/basic-istringstream-class.md) 템플릿 클래스와 동일한 의미입니다*.*  
  
##  <a name="a-nameostringstreama--ostringstream"></a><a name="ostringstream"></a>  ostringstream  
 `char` 템플릿 매개 변수에 대해 특수화된 `basic_ostringstream` 형식을 만듭니다.  
  
```  
typedef basic_ostringstream<char> ostringstream;  
```  
  
### <a name="remarks"></a>설명  
 이 형식은 `char` 형식의 요소용으로 특수화된 [basic_ostringstream](../standard-library/basic-ostringstream-class.md) 템플릿 클래스와 동일한 의미입니다*.*  
  
##  <a name="a-namestringbufa--stringbuf"></a><a name="stringbuf"></a>  stringbuf  
 `char` 템플릿 매개 변수에 대해 특수화된 `basic_stringbuf` 형식을 만듭니다.  
  
```  
typedef basic_stringbuf<char> stringbuf;  
```  
  
### <a name="remarks"></a>설명  
 이 형식은 `char` 형식의 요소용으로 특수화된 [basic_stringbuf](../standard-library/basic-stringbuf-class.md) 템플릿 클래스와 동일한 의미입니다*.*  
  
##  <a name="a-namestringstreama--stringstream"></a><a name="stringstream"></a>  stringstream  
 `char` 템플릿 매개 변수에 대해 특수화된 `basic_stringstream` 형식을 만듭니다.  
  
```  
typedef basic_stringstream<char> stringstream;  
```  
  
### <a name="remarks"></a>설명  
 이 형식은 `char` 형식의 요소용으로 특수화된 [basic_stringstream](../standard-library/basic-stringstream-class.md) 템플릿 클래스와 동일한 의미입니다*.*  
  
##  <a name="a-namewistringstreama--wistringstream"></a><a name="wistringstream"></a>  wistringstream  
 `wchar_t` 템플릿 매개 변수에 대해 특수화된 `basic_istringstream` 형식을 만듭니다.  
  
```  
typedef basic_istringstream<wchar_t> wistringstream;  
```  
  
### <a name="remarks"></a>설명  
 이 형식은 `wchar_t` 형식의 요소용으로 특수화된 [basic_istringstream](../standard-library/basic-istringstream-class.md) 템플릿 클래스와 동일한 의미입니다.  
  
##  <a name="a-namewostringstreama--wostringstream"></a><a name="wostringstream"></a>  wostringstream  
 `wchar_t` 템플릿 매개 변수에 대해 특수화된 `basic_ostringstream` 형식을 만듭니다.  
  
```  
typedef basic_ostringstream<wchar_t> wostringstream;  
```  
  
### <a name="remarks"></a>설명  
 이 형식은 `wchar_t` 형식의 요소용으로 특수화된 [basic_ostringstream](../standard-library/basic-ostringstream-class.md) 템플릿 클래스와 동일한 의미입니다.  
  
##  <a name="a-namewstringbufa--wstringbuf"></a><a name="wstringbuf"></a>  wstringbuf  
 `wchar_t` 템플릿 매개 변수에 대해 특수화된 `basic_stringbuf` 형식을 만듭니다.  
  
```  
typedef basic_stringbuf<wchar_t> wstringbuf;  
```  
  
### <a name="remarks"></a>설명  
 이 형식은 `wchar_t` 형식의 요소용으로 특수화된 [basic_stringbuf](../standard-library/basic-stringbuf-class.md) 템플릿 클래스와 동일한 의미입니다.  
  
##  <a name="a-namewstringstreama--wstringstream"></a><a name="wstringstream"></a>  wstringstream  
 `wchar_t` 템플릿 매개 변수에 대해 특수화된 `basic_stringstream` 형식을 만듭니다.  
  
```  
typedef basic_stringstream<wchar_t> wstringstream;  
```  
  
### <a name="remarks"></a>설명  
 이 형식은 `wchar_t` 형식의 요소용으로 특수화된 [basic_stringstream](../standard-library/basic-stringstream-class.md) 템플릿 클래스와 동일한 의미입니다.  
  
## <a name="see-also"></a>참고 항목  
 [\<sstream>](../standard-library/sstream.md)


