---
title: "Agile::GetAddressOfForInOut 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "agile/Platform::Agile::GetAddressOfForInOut"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::Agile::GetAddressOfForInOut"
ms.assetid: 8bb27b4c-c325-49ee-91db-9adf87c530c4
caps.latest.revision: 2
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Agile::GetAddressOfForInOut 메서드
현재 Agile 개체가 나타내는 개체에 대한 핸들의 주소를 반환합니다.  
  
## 구문  
  
```cpp  
  
       T^* GetAddressOfForInOut()   
throw();  
  
```  
  
#### 매개 변수  
 `T`  
 템플릿 형식 이름 매개 변수로 지정된 형식입니다.  
  
## 반환 값  
 현재 Agile 개체가 나타내는 개체에 대한 핸들의 주소입니다.  
  
## 설명  
 이 작업은 현재 스레딩 컨텍스트를 가져온 다음 내부 개체에 대한 핸들의 주소를 반환합니다.  
  
## 요구 사항  
 **지원되는 최소 클라이언트:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **지원되는 최소 서버:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **네임스페이스:** Platform  
  
 **헤더:** vccorlib.h  
  
## 참고 항목  
 [Platform::Agile 클래스](../cppcx/platform-agile-class.md)