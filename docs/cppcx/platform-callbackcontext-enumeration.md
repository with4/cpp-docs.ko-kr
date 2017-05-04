---
title: "Platform::CallbackContext 열거형 | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::CallbackContext"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::CallbackContext 열거형"
ms.assetid: 60e0c7cb-5d8f-482a-bdca-ca9335ae4899
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 3
---
# Platform::CallbackContext 열거형
콜백 함수\(이벤트 처리기\)가 실행되는 스레드 컨텍스트를 지정합니다.  
  
## 구문  
  
```cpp  
enum class CallbackContext {};  
```  
  
## 멤버  
  
|형식 코드|설명|  
|-----------|--------|  
|임의의 값|콜백 함수가 모든 스레드 컨텍스트에서 실행될 수 있습니다.|  
|왼쪽과 같음|콜백 함수가 비동기 작업을 시작한 스레드 컨텍스트에서만 실행될 수 있습니다.|  
  
## 요구 사항  
 **지원되는 최소 클라이언트:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **지원되는 최소 서버:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **네임스페이스:** Platform  
  
 **메타데이터:** platform.winmd