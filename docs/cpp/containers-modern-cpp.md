---
title: "컨테이너 (최신 c + +) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 6e10b758-e928-4827-9c3f-86cafe54bf5b
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4fc8bbc3a983e6fa50e4ae5e8590e1f1de37f02f
ms.sourcegitcommit: ff9bf140b6874bc08718674c07312ecb5f996463
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="containers-modern-c"></a>컨테이너(최신 C++)  
  
기본적으로 사용 하 여 [벡터](../standard-library/vector-class.md) c + +에서 기본 순차적 컨테이너입니다. 이에 해당 하는 `List<T>` .NET 언어에서입니다.  
  
```cpp  
vector<string> apples;  
apples.push_back("Granny Smith");  
```  
  
사용 하 여 [지도](../standard-library/map-class.md) (하지 `unordered_map`) 기본 연관 컨테이너입니다. 사용 하 여 [설정](../standard-library/set-class.md), [multimap](../standard-library/multimap-class.md), 및 [multiset](../standard-library/multiset-class.md) 중복 제거 및 다중 사례에 대 한 합니다.  
  
```cpp  
map<string, string> apple_color;  
// ...  
apple_color["Granny Smith"] = "Green";  
```  
  
성능 최적화에 필요한 경우 사용 하십시오.  
  
1.  [배열](../standard-library/array-class-stl.md) 포함 하는 것이 중요 클래스 멤버 등으로 입력 합니다.  
  
2.  연관 컨테이너와 같은 순서가 지정 되지 않은 [unordered_map](../standard-library/unordered-map-class.md)합니다. 이러한 하위 요소 오버 헤드 포함 하 고 일정 시간 조회 있지만 올바르고 효율적으로 사용 하기 쉽다는 점 수 있습니다.  
  
3.  정렬 `vector`합니다. 자세한 내용은 [알고리즘](../cpp/algorithms-modern-cpp.md)을 참조하세요.  
  
C 스타일 배열에 사용 하지 마십시오. 데이터에 대 한 액세스를 지시 해야 하는 오래 된 Api에 대 한 접근자와 같은 메서드 사용 `f(vec.data(), vec.size());` 대신 합니다.  
  
컨테이너에 대 한 자세한 내용은 참조 [c + + 표준 라이브러리 컨테이너](../standard-library/stl-containers.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [C + +의 진화](../cpp/welcome-back-to-cpp-modern-cpp.md)   
 [C + + 언어 참조](../cpp/cpp-language-reference.md)   
 [C++ 표준 라이브러리](../standard-library/cpp-standard-library-reference.md)
