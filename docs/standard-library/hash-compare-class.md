---
title: "hash_compare 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "hash_set/stdext::hash_compare"
  - "std.hash_compare"
  - "hash_compare"
  - "std::hash_compare"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "hash_compare 클래스"
ms.assetid: d502bb59-de57-4585-beb9-00e3a998c0af
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# hash_compare 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 템플릿 클래스는 해시 연관 컨테이너\(hash\_map, hash\_multimap, hash\_set 또는 hash\_multiset\) 중 하나에서 기본 **Traits** 매개 변수 개체로 사용하여 포함된 요소의 순서를 지정하고 해시할 수 있는 개체를 설명합니다.  
  
## 구문  
  
```  
template<class Key, class Traits = less<Key> >  
   class hash_compare  
   {  
   Traits comp;  
public:  
   const size_t bucket_size = 4;  
   const size_t min_buckets = 8;  
   hash_compare( );  
   hash_compare( Traits pred );  
   size_t operator( )( const Key& _Key ) const;  
   bool operator( )(   
      const Key& _Key1,  
      const Key& _Key2  
   ) const;  
   };  
```  
  
## 설명  
 각 해시 연관 컨테이너는 **Traits**\(템플릿 매개 변수\) 형식의 해시 특성 개체를 저장합니다.  hash\_compare 특수화에서 클래스를 파생시켜 특정 함수 및 개체를 선택적으로 재정의하거나, 최소한의 특정 요구를 충족하는 경우 이 클래스의 고유한 버전을 제공할 수 있습니다.  특히 **hash\_compare\<Key, Traits\>** 형식의 개체 hash\_comp에서는 위의 컨테이너에 다음과 같은 동작이 필요합니다.  
  
-   **Key** 형식의 모든 값 `_Key`에 대해 **hash\_comp**\(`_Key`\) 호출은 **size\_t** 형식의 값 분포를 생성하는 해시 함수 역할을 합니다.  hash\_compare에서 제공하는 함수는 `_Key`를 반환합니다.  
  
-   시퀀스에서 `_Key2` 앞에 오고 동일한 해시 값\(해시 함수에서 반환된 값\)을 가진 **Key** 형식의 모든 값 `_Key1`에 대해 **hash\_comp**\(`_Key2`, `_Key1`\)는 false입니다.  함수가 **Key** 형식의 값에 전체 순서 지정을 적용해야 합니다.  Hash\_compare에서 제공하는 함수는 *comp*\(`_Key2`, `_Key1`\)`,`을 반환합니다. 여기서 *comp*는 개체 hash\_comp를 생성할 때 지정할 수 있는 **Traits** 형식의 저장된 개체입니다.  기본 **Traits** 매개 변수 형식 **less\<Key\>**에 대해 정렬 키 값은 결코 감소하지 않습니다.  
  
-   정수 상수 **bucket\_size**는 컨테이너가 초과하지 않도록 해야 하는 "버킷당"\(해시 테이블 항목\) 평균 요소 수를 지정합니다.  0보다 커야 합니다.  hash\_compare에서 제공하는 값은 4입니다.  
  
-   정수 상수 **min\_buckets**는 해시 테이블에서 유지할 최소 버킷 수를 지정합니다.  0보다 큰 2의 거듭제곱이어야 합니다.  hash\_compare에서 제공하는 값은 8입니다.  
  
 Visual C\+\+ .NET 2003에서 [\<hash\_map\>](../standard-library/hash-map.md) 및 [\<hash\_set\>](../standard-library/hash-set.md) 헤더 파일의 멤버는 더 이상 std 네임스페이스에 없으며, 대신 stdext 네임스페이스로 이동되었습니다.  자세한 내용은 [stdext 네임스페이스](../standard-library/stdext-namespace.md)를 참조하세요.  
  
## 예제  
 hash\_compare를 선언 및 사용하는 방법의 예제는 [hash\_map::hash\_map](../Topic/hash_map::hash_map.md), [hash\_multimap::hash\_multimap](../Topic/hash_multimap::hash_multimap.md), [hash\_set::hash\_set](../Topic/hash_set::hash_set.md) 및 [hash\_multiset::hash\_multiset](../Topic/hash_multiset::hash_multiset.md)에 대한 예제를 참조하세요.  
  
## 요구 사항  
 **헤더:** \<hash\_map\>  
  
 **네임스페이스:** stdext  
  
## 참고 항목  
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [표준 템플릿 라이브러리](../misc/standard-template-library.md)