---
title: "COMException::HResult 속성 | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::COMException::HResult"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COMException::HResult 속성"
ms.assetid: 53762ab5-ce71-4397-b7b4-8175741c838f
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# COMException::HResult 속성
예외에 해당하는 HRESULT입니다.  
  
## 구문  
  
```cpp  
public:property int HResult {    int get();}  
```  
  
## 속성 값  
 오류를 지정하는 HRESULT 값입니다.  
  
## 설명  
 HRESULT 값을 해석하는 방법에 대한 자세한 내용은 [COM 오류 코드 구조](http://go.microsoft.com/fwlink/p/?LinkId=262045)를 참조하세요.  
  
## 요구 사항  
 **지원되는 최소 클라이언트:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **지원되는 최소 서버:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **네임스페이스:** Platform  
  
 **헤더:** vccorlib.h  
  
## 하위 단원 제목  
  
## 참고 항목  
 [Platform::COMException 클래스](../cppcx/platform-comexception-class.md)