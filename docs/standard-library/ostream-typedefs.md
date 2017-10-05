---
title: "&lt;ostream&gt; 형식 정의 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- iosfwd/std::ostream
- iosfwd/std::wostream
ms.assetid: 2ec4dc52-a01f-4654-bd65-dd5288777c48
caps.latest.revision: 11
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: bcf7df720a9b3a71ddbb32bd6eeb73f2f1332391
ms.contentlocale: ko-kr
ms.lasthandoff: 10/03/2017

---
# <a name="ltostreamgt-typedefs"></a>&lt;ostream&gt; 형식 정의
|||  
|-|-|  
|[ostream](#ostream)|[wostream](#wostream)|  
  
##  <a name="ostream"></a>  ostream  
 `char`에서 특수화된 basic_ostream 및 `char`에서 특수화된 `char_traits`를 통해 형식을 만듭니다.  
  
```
typedef basic_ostream<char, char_traits<char>> ostream;
```  
  
### <a name="remarks"></a>설명  
 이 형식은 기본 문자 특성을 포함하는 `char` 형식의 요소용으로 특수화된 [basic_ostream](../standard-library/basic-ostream-class.md) 템플릿 클래스와 동일한 의미입니다.  
  
##  <a name="wostream"></a>  wostream  
 `wchar_t`에서 특수화된 basic_ostream 및 `wchar_t`에서 특수화된 `char_traits`를 통해 형식을 만듭니다.  
  
```
typedef basic_ostream<wchar_t, char_traits<wchar_t>> wostream;
```  
  
### <a name="remarks"></a>설명  
 이 형식은 기본 문자 특성을 포함하는 `wchar_t` 형식의 요소용으로 특수화된 [basic_ostream](../standard-library/basic-ostream-class.md) 템플릿 클래스와 동일한 의미입니다.  
  
## <a name="see-also"></a>참고 항목  
 [\<ostream>](../standard-library/ostream.md)




