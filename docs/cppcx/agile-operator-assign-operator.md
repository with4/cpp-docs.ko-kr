---
title: "Agile::operator= 연산자 | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "agile/Platform::Agile::operator="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::Agile::operator="
ms.assetid: 2c413bef-f103-4911-afb3-0dac5f6a760e
caps.latest.revision: 2
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Agile::operator= 연산자
지정한 개체를 현재 Agile 개체에 할당합니다.  
  
## 구문  
  
```cpp  
  
   Agile<T> operator=(  
   T^ object  
) throw();  
  
   Agile<T> operator=(  
      const Agile<T>& object  
) throw();  
  
   Agile<T> operator=(  
      Agile<T>&& object  
) throw();  
  
   T^ operator=(  
      IUnknown* lp  
) throw();  
  
```  
  
#### 매개 변수  
 `T`  
 템플릿 typename으로 지정된 형식입니다.  
  
 `object`  
 현재 Agile 개체로 복사되거나 이동된 개체 또는 개체의 핸들입니다.  
  
 `lp`  
 개체의 IUnknown 인터페이스 포인터입니다.  
  
## 반환 값  
 `T` 형식의 개체에 대한 핸들입니다.  
  
## 설명  
 첫 번째 버전의 할당 연산자는 참조 형식의 핸들을 현재 Agile 개체에 복사합니다. 두 번째 버전은 Agile 형식에 대한 참조를 현재 Agile 개체에 복사합니다. 세 번째 버전은 Agile 형식을 현재 Agile 개체로 이동합니다. 네 번째 버전은 COM 개체의 포인터를 현재 Agile 개체로 이동합니다.  
  
 할당 연산은 현재 Agile 개체의 컨텍스트를 자동으로 유지합니다.  
  
## 요구 사항  
 **지원되는 최소 클라이언트:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **지원되는 최소 서버:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **네임스페이스:** Platform  
  
 **헤더:** vccorlib.h  
  
## 참고 항목  
 [Platform::Agile 클래스](../cppcx/platform-agile-class.md)