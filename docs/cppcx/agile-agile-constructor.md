---
title: "Agile::Agile 생성자 | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "agile/Platform::Agile::Agile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::Agile::Agile"
ms.assetid: 33c1df82-f5db-4750-98cc-0daa03be4e59
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Agile::Agile 생성자
Agile 클래스의 새 인스턴스를 초기화합니다.  
  
## 구문  
  
```cpp  
  
 Agile();  
  
Agile(T^ object);   
  
Agile(const Agile<T>& object);  
  
Agile(Agile<T>&& object);  
  
```  
  
#### 매개 변수  
 `T`  
 템플릿 형식 이름 매개 변수로 지정된 형식입니다.  
  
 `object`  
 이 생성자의 두 번째 버전에서 새 Agile 인스턴스를 초기화하기 위해 사용된 개체입니다. 이 생성자의 세 번째 버전에서 새 Agile 인스턴스에 복사된 개체입니다. 이 생성자의 네 번째 버전에서 새 Agile 인스턴스로 이동된 개체입니다.  
  
## 설명  
 이 생성자의 첫 번째 버전은 기본 생성자입니다. 두 번째 버전은 `object` 매개 변수로 지정된 개체에서 새 Agile 인스턴스 클래스를 초기화합니다. 세 번째 버전은 복사 생성자입니다. 네 번째 버전은 이동 생성자입니다. 이 생성자는 예외를 throw할 수 없습니다.  
  
## 요구 사항  
 **지원되는 최소 클라이언트:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **지원되는 최소 서버:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **네임스페이스:** Platform  
  
 **헤더:** vccorlib.h  
  
## 참고 항목  
 [Platform::Agile 클래스](../cppcx/platform-agile-class.md)