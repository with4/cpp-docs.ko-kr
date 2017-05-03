---
title: "Map::Map 생성자 | Microsoft Docs"
ms.custom: ""
ms.date: "01/25/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::Map::Map"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Map::Map 생성자"
ms.assetid: 4cd314eb-e3e3-4fa7-8c58-96e48d167246
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Map::Map 생성자
Map 클래스의 새 인스턴스를 초기화합니다.  
  
## 구문  
  
```  
explicit Map(  
   const C& comp = C()  
);  
explicit Map(  
   const StdMap& m  
);  
explicit Map(  
   StdMap&& m  
);  
template <  
   typename InIt  
>  
Map(  
   InItfirst,  
   InItlast,  
   const C& comp = C()  
);  
```  
  
#### 매개 변수  
 `InIt`  
 현재 Map의 형식 이름입니다.  
  
 `comp`  
 두 요소 값을 정렬 키로 비교하여 맵에서 해당 상대 순서를 확인할 수 있는 함수 개체를 제공하는 형식입니다.  
  
 `m`  
 현재 Map을 초기화하는 데 사용되는 [Lvalue 및 Rvalue](~/cpp/lvalues-and-rvalues-visual-cpp.md)에 대한 참조 또는 [map 클래스](../standard-library/map-class.md)입니다.  
  
 `first`  
 현재 Map를 초기화하는 데 사용되는 요소 범위에서 첫 번째 요소의 입력 반복기입니다.  
  
 `last`  
 현재 Map를 초기화하는 데 사용되는 요소 범위 다음의 첫 번째 요소의 입력 반복기입니다.  
  
## 요구 사항  
 **헤더:** collection.h  
  
 **네임스페이스:** Platform::Collections  
  
## 참고 항목  
 [Platform::Collections::Map 클래스](../cppcx/platform-collections-map-class.md)