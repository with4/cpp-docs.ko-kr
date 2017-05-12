---
title: "Platform::IBoxArray 인터페이스 | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::IBoxArray"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::IBoxArray"
ms.assetid: 6cd82c9e-4230-4147-9edb-7a652875dbf1
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 5
---
# Platform::IBoxArray 인터페이스
`IBoxArray`는 XAML 컨트롤의 요소와 같은 `Platform::Object^` 요소의 컬렉션에 저장되거나 ABI\(응용 프로그램 이진 인터페이스\)를 통해 전달되는 값 형식의 배열에 대한 래퍼입니다.  
  
## 구문  
  
```cpp  
template <typename T>  
interface class IBoxArray  
```  
  
#### 매개 변수  
 `T`  
 각 배열 요소의 boxed 값 형식입니다.  
  
## 설명  
 `IBoxArray`는 [!INCLUDE[cppwrt](../cppcx/includes/cppwrt-md.md)]의 [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]\(`Windows::Foundation::IReferenceArray`\) 이름입니다.  
  
## 멤버  
 `IBoxArray` 인터페이스는 `IValueType` 인터페이스에서 상속됩니다.`IBoxArray`에도 다음과 같은 멤버가 포함됩니다.  
  
|메서드|설명|  
|---------|--------|  
|값|이 `IBoxArray` 인스턴스에 이전에 저장된 unboxed 배열을 반환합니다.|  
  
## 참고 항목  
 [Array 및 WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md)