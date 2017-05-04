---
title: "Agile::GetAddressOf 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "agile/Platform::Agile::GetAddressOf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::Agile::GetAddressOf"
ms.assetid: f015edf9-4155-4992-a6fc-7ff1edcc5d1e
caps.latest.revision: 2
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Agile::GetAddressOf 메서드
현재 Agile 개체를 다시 초기화하고 핸들 주소를 `T` 형식 개체에 반환합니다.  
  
## 구문  
  
```cpp  
  
       T^* GetAddressOf()   
throw();  
```  
  
#### 매개 변수  
 `T`  
 템플릿 형식 이름 매개 변수로 지정된 형식입니다.  
  
## 반환 값  
 `T` 형식의 개체에 대한 핸들의 주소입니다.  
  
## 설명  
 이 작업은 `T` 형식의 개체에 대한 현재 표시를 해제하고\(있는 경우\), Agile 개체의 데이터 멤버를 다시 초기화하고, 현재 스레딩 컨텍스트를 가져오고 나서, agile이 아닌 개체를 나타낼 수 있는 개체 핸들 변수의 주소를 반환합니다. Agile 클래스 인스턴스가 개체를 표시하게 하려면 대입 연산자\([Agile::operator\=](../cppcx/agile-operator-assign-operator.md)\)를 사용하여 개체를 Agile 클래스 인스턴스에 할당합니다.  
  
## 요구 사항  
 **지원되는 최소 클라이언트:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **지원되는 최소 서버:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **네임스페이스:** Platform  
  
 **헤더:** vccorlib.h  
  
## 참고 항목  
 [Platform::Agile 클래스](../cppcx/platform-agile-class.md)