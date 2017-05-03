---
title: "Exception::HResult 속성 | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Exception::HResult"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Exception::HResult 속성"
ms.assetid: 24ef008d-6884-4b8b-9556-41bfa6e1edf1
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Exception::HResult 속성
예외에 해당하는 HRESULT입니다.  
  
## 구문  
  
```cpp  
public:property int HResult {    int get();}  
```  
  
## 속성 값  
 HRESULT 값입니다.  
  
## 설명  
 대부분의 예외는 HRESULT 값으로 반환되는 COM 오류로 시작합니다. C\+\+\/CX가 이러한 값을 Platform::Exception^ 개체로 변환하고, 이 속성이 원래 오류 코드의 값을 저장합니다.  
  
## 요구 사항  
 **지원되는 최소 클라이언트:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **지원되는 최소 서버:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **네임스페이스:** Platform  
  
 **메타데이터:** platform.winmd  
  
## 참고 항목  
 [Platform::Exception 클래스](../cppcx/platform-exception-class.md)