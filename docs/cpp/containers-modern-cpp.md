---
title: "컨테이너(최신 C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 6e10b758-e928-4827-9c3f-86cafe54bf5b
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 컨테이너(최신 C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

기본적으로 사용 하 여 [벡터](../standard-library/vector-class.md) c + +에서 기본 순차 컨테이너입니다. 이 목록에 해당 하는 \< T> 다른 언어에서입니다.  
  
```cpp  
vector<string> v;  
v.push_back( "Geddy Lee" );  
  
```  
  
 사용 하 여 [맵](../standard-library/map-class.md) (unordered_map) 기본 연관 컨테이너입니다. 사용 하 여 [설정](../standard-library/set-class.md), [multimap](../standard-library/multimap-class.md), [multiset](../standard-library/multiset-class.md) 중복 제거 및 다중 경우.  
  
```cpp  
map<string, string> phone_book;  
// ...  
phone_book["Alex Lifeson"] = "+1 (416) 555-1212";  
  
```  
  
 와 성능 최적화가 필요한 경우 사용 하는 것이 좋습니다.  
  
1.  배열 형식을 포함할 때 중요-예를 들어 클래스 멤버로 합니다.  
  
2.  순서가 지정되지 않은 연관 컨테이너(unordered_map, et al): 요소마다 오버헤드 낮추고(주요) 및 일정한 시간 조회(잠재적 주요, 경우에 따라 부차적)합니다. 날카로운 가장자리와 불편함으로 인해 정확하고 효율적으로 사용하기 어렵습니다.  
  
3.  정렬된 벡터입니다. (참조: [알고리즘](../cpp/algorithms-modern-cpp.md).)  
  
 C 배열과 사용 하지 마십시오. (이전 Api를 사용 하 여 `f( vec.data(), vec.size() );` .)  
  
 컨테이너에 대 한 다른 문서를 참조 하십시오. [STL 컨테이너](../standard-library/stl-containers.md)합니다.  
  
## <a name="container-sizes"></a>컨테이너 크기  
 다음 표에서 x86 및 x64 플랫폼에 대 한 바이트의 컨테이너 크기를 나타냅니다.  (이러한 목적을 위해 32 비트 ARM은 x86.)  이러한 테이블 공간 및 시간을 소비 하는 검사 메커니즘을 포함 하는 디버그 모드 때문에 릴리스 모드를 처리 합니다.  에 대 한 별도 열은 [!INCLUDE[cpp_orcas_long](../cpp/includes/cpp_orcas_long_md.md)] s p 1에서는 여기서 `_SECURE_SCL` 기본적으로 1로 등에 [!INCLUDE[cpp_orcas_long](../cpp/includes/cpp_orcas_long_md.md)] s p 1과 `_SECURE_SCL` 수동으로 최대 속도 0으로 설정 합니다.  Visual Studio 2010에서 visual c + + [!INCLUDE[cpp_dev11_long](../build/includes/cpp_dev11_long_md.md)], 및 [!INCLUDE[cpp_dev12_long](../build/reference/includes/cpp_dev12_long_md.md)] 기본 `_SECURE_SCL` 0 (현재 명칭 `_ITERATOR_DEBUG_LEVEL`).  
  
|x86 컨테이너 크기 (바이트)|VC9 SP1|VC9 SP1<br /><br /> SCL=0|VC10|VC11|  
|-----------------------------------|-------------|------------------------|----------|----------|  
|벡터 \< int>|24|16|16|12|  
|\< int, 5 > 배열|20|20|20|20|  
|q u e \< int>|32|32|24|20|  
|forward_list \< int>|N/A|N/A|8|4|  
|목록 \< int>|28|12|12|8|  
|priority_queue \< int>|28|20|20|16|  
|큐 \< int>|32|32|24|20|  
|스택 \< int>|32|32|24|20|  
|\< int, int > 쌍|9|8|8|8|  
|튜플 \< int, int, int >|16|16|16|12|  
|지도 \< int, int >|32|12|16|9|  
|multimap \< int, int >|32|12|16|8|  
|설정 \< int>|32|12|16|8|  
|multiset \< int>|32|12|16|8|  
|hash_map \< int, int >|72|44|44|32|  
|hash_multimap \< int, int >|72|44|44|32|  
|hash_set \< int>|72|44|44|32|  
|hash_multiset \< int>|72|44|44|32|  
|unordered_map \< int, int >|72|44|44|32|  
|unordered_multimap \< int, int >|72|44|44|32|  
|unordered_set \< int>|72|44|44|32|  
ordered_multiset \< int>|72|44|44|32|  
|string|28|28|28|24|  
|wstring|28|28|28|24|  
  
|x64 컨테이너 크기 (바이트)|VC9 SP1|VC9 SP1<br /><br /> SCL=0|VC10|VC11|  
|-----------------------------------|-------------|------------------------|----------|----------|  
|벡터 \< int>|48|32|32|24|  
|\< int, 5 > 배열|20|20|20|20|  
|q u e \< int>|64|64|48|40|  
|forward_list \< int>|N/A|N/A|16|8|  
|목록 \< int>|56|24|24|16|  
|priority_queue \< int>|56|40|40|32|  
|큐 \< int>|64|64|48|40|  
|스택 \< int>|64|64|48|40|  
|\< int, int > 쌍|9|8|8|8|  
|튜플 \< int, int, int >|16|16|16|12|  
|지도 \< int, int >|64|24|32|16|  
|multimap \< int, int >|64|24|32|16|  
|설정 \< int>|64|24|32|16|  
|multiset \< int>|64|24|32|16|  
|hash_map \< int, int >|144|88|88|64|  
|hash_multimap \< int, int >|144|88|88|64|  
|hash_set \< int>|144|88|88|64|  
|hash_multiset \< int>|144|88|88|64|  
|unordered_map \< int, int >|144|88|88|64|  
|unordered_multimap \< int, int >|144|88|88|64|  
|unordered_set \< int>|144|88|88|64|  
ordered_multiset \< int>|144|88|88|64|  
|string|40|40|40|32|  
|wstring|40|40|40|32|  
  
## <a name="see-also"></a>참고 항목  
 [C + +의 진화](../cpp/welcome-back-to-cpp-modern-cpp.md)   
 [C + + 언어 참조](../cpp/cpp-language-reference.md)   
 [C + + 표준 라이브러리](../standard-library/cpp-standard-library-reference.md)