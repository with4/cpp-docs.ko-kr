---
title: "Object::ToString 메서드(C++/CX) | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Object::ToString"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform, Object::ToString"
ms.assetid: 229dbf1c-cb43-4ed2-a1c5-a1f36b22a7ea
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Object::ToString 메서드(C++/CX)
현재 개체를 나타내는 문자열을 반환합니다.  
  
## 구문  
  
```cpp  
public:  
virtual String^ ToString()  
```  
  
## 반환 값  
 현재 개체를 나타내는 문자열입니다. 이 메서드를 재정의하여 ref 클래스 또는 구조체에서 사용자 지정 문자열 메시지를 제공할 수 있습니다.  
  
```cpp  
public ref class Tree sealed { public: Tree(){} virtual Platform::String^ ToString()override { return "I’m a Tree"; }; };  
```  
  
## 요구 사항  
 **지원되는 최소 클라이언트:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **지원되는 최소 서버:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **네임스페이스:** Platform  
  
 **헤더:** vccorlib.h  
  
## 참고 항목  
 [Platform::Object 클래스](../cppcx/platform-object-class.md)