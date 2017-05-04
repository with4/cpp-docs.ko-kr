---
title: "Type::FullName 속성 | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Type::get_FullName"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Type::get_FullName 속성"
ms.assetid: b5a12d8f-4404-4659-b4af-e7d23a1e44b7
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Type::FullName 속성
현재 형식의 정규화된 이름을 "Namespace.Type" 형식으로 검색합니다.  
  
## 구문  
  
```cpp  
String^ FullName();  
```  
  
## 반환 값  
 형식의 이름입니다.  
  
## 예제  
  
```  
  
//  namespace is TestApp MainPage::MainPage() { InitializeComponent(); Type^ t = this->GetType(); auto s = t->FullName; // returns “TestApp.MainPage” auto s2 = t->ToString(); //also returns “TestApp.MainPage” }  
```  
  
## 요구 사항  
 **지원되는 최소 클라이언트:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **지원되는 최소 서버:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **네임스페이스:** Platform  
  
 **메타데이터:** platform.winmd  
  
## 참고 항목  
 [Platform::ValueType 클래스](../cppcx/platform-valuetype-class.md)