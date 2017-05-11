---
title: "&lt;vector&gt; 함수 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: []
ms.assetid: 6cdcf043-eef6-4330-83f0-4596fb9f968a
caps.latest.revision: 10
manager: ghogen
ms.translationtype: Machine Translation
ms.sourcegitcommit: 4ecf60434799708acab4726a95380a2d3b9dbb3a
ms.openlocfilehash: 239ac662d19e3d0aa788e830557c28bc84835828
ms.contentlocale: ko-kr
ms.lasthandoff: 04/19/2017

---
# <a name="ltvectorgt-functions"></a>&lt;vector&gt; 함수

  
##  <a name="swap"></a>  swap  
 두 벡터의 요소를 교환합니다.  
  
```  
template <class Type, class Allocator>  
void swap(vector<Type, Allocator>& left, vector<Type, Allocator>& right);
```  
  
### <a name="parameters"></a>매개 변수  
 `right`  
 교환할 요소를 제공하는 벡터이거나, `left` 벡터와 요소를 교환할 벡터입니다.  
  
 `left`  
 `right` 벡터와 요소를 교환할 벡터입니다.  
  
### <a name="remarks"></a>주의  
 템플릿 함수는 멤버 함수를 실행 하는 컨테이너 클래스 벡터에 `left`합니다. [vector:: swap](../standard-library/vector-class.md) *(오른쪽*). 이러한 함수는 컴파일러에서 지정하는 함수 템플릿의 부분 순서 인스턴스입니다. 템플릿 함수가 이러한 방식으로 오버로드되어 함수를 호출할 때 템플릿이 고유하게 일치하지 않으면 컴파일러는 템플릿 함수의 가장 특수화된 버전을 선택합니다. 알고리즘 클래스에서 템플릿 함수의 일반 버전인 **template** \< **class T**> **void swap**( **T&**, **T&**)는 할당을 기준으로 작동하며 속도가 느린 작업입니다. 각 컨테이너의 특수화된 버전은 컨테이너 클래스의 내부 표현을 사용할 수 있으므로 속도가 훨씬 빠릅니다.  
  
### <a name="example"></a>예제  
  `swap`의 템플릿 버전을 사용하는 예제를 확인하려면 구성원 함수 [vector:: swap](../standard-library/vector-class.md)의 코드 예제를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [\<vector>](../standard-library/vector.md)


