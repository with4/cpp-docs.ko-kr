---
title: "Platform::ArrayReference 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::ArrayReference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::ArrayReference 클래스"
ms.assetid: 9ab3b15e-8a60-4600-8fcb-7d6c86284f4b
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 4
---
# Platform::ArrayReference 클래스
`ArrayReference`는 C 스타일 배열을 입력 데이터로 채울 때 입력 매개 변수에서 [Platform::Array^](../cppcx/platform-array-class.md)를 대체할 수 있는 최적화 형식입니다.  
  
## 구문  
  
```vb  
  
```  
  
```csharp  
  
```  
  
## 멤버  
  
### Public 생성자  
  
|이름|설명|  
|--------|--------|  
|[ArrayReference::ArrayReference 생성자](../cppcx/arrayreference-arrayreference-constructor.md)|`ArrayReference` 클래스의 새 인스턴스를 초기화합니다.|  
  
### Public 연산자  
  
|이름|설명|  
|--------|--------|  
|[ArrayReference::operator\(\) 연산자](../cppcx/arrayreference-operator-call-operator.md)|이 `ArrayReference`를 `Platform::Array<T>^*`로 변환합니다.|  
|[ArrayReference::operator\= 연산자](../cppcx/arrayreference-operator-assign-operator.md)|다른 `ArrayReference`의 내용을 이 인스턴스에 할당합니다.|  
  
## 예외  
  
## 설명  
 `ArrayReference`를 사용하여 C 스타일 배열을 채워서 먼저 `Platform::Array` 변수로 복사한 다음 C 스타일 배열로 복사하는 추가적인 복사 작업을 피합니다.`ArrayReference`를 사용하면 한 번의 복사 작업만 있습니다. 코드 예제를 보려면 [Array 및 WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md)를 참조하세요.  
  
## 요구 사항  
 **지원되는 최소 클라이언트:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **지원되는 최소 서버:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **네임스페이스:** Platform  
  
 **헤더:** vccorlib.h  
  
## 하위 단원 제목  
  
## 참고 항목  
 [Platform 네임스페이스](../cppcx/platform-namespace-c-cx.md)