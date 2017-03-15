---
title: "&lt;istream&gt; 함수 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0301ea0d-4ded-4841-83dd-4253b55b3188
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: aa35f177bcb986e141d0e46e48dc007a96f94498
ms.lasthandoff: 02/24/2017

---
# <a name="ltistreamgt-functions"></a>&lt;istream&gt; 함수
|||  
|-|-|  
|[swap](#istream_swap)|[ws](#ws)|  
  
##  <a name="a-nameistreamswapa--swap"></a><a name="istream_swap"></a>  swap  
 두 stream 개체의 요소를 교환합니다.  
  
```  
template <class Elem, class Tr>  
void swap(
    basic_istream<Elem, Tr>& left,  
    basic_istream<Elem, Tr>& right);

template <class Elem, class Tr>  
void swap(
    basic_iostream<Elem, Tr>& left,  
    basic_iostream<Elem, Tr>& right);
```  
  
### <a name="parameters"></a>매개 변수  
 ` left`  
 스트림입니다.  
  
 ` right`  
 스트림입니다.  
  
##  <a name="a-namewsa--ws"></a><a name="ws"></a>  ws  
 스트림의 공백을 건너뜁니다.  
  
```  
template class<Elem, Tr> basic_istream<Elem, Tr>& ws(basic_istream<Elem, Tr>& _Istr);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Istr`  
 스트림입니다.  
  
### <a name="return-value"></a>반환 값  
 스트림입니다.  
  
### <a name="remarks"></a>설명  
 이 조작자는 모든 `ch` 요소(이 요소의 경우 [use_facet](../standard-library/basic-filebuf-class.md#basic_filebuf__open)< **ctype**\< **Elem**> >( [getloc](../standard-library/ios-base-class.md#ios_base__getloc)). **is**( **ctype**\< **Elem**>:: **space**, **ch**)가 true임)를 추출하고 삭제합니다.  
  
 함수는 요소를 추출하는 동안 파일 끝에 도달하면 [setstate](../standard-library/basic-ios-class.md#basic_ios__setstate)( **eofbit**)를 호출합니다. `_Istr`를 반환합니다.  
  
### <a name="example"></a>예제  
  `ws` 사용 예제는 [operator>>](../standard-library/istream-operators.md#operator_gt__gt_)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [\<istream>](../standard-library/istream.md)


