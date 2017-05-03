---
title: "Platform::StringReference 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::StringReference"
dev_langs: 
  - "C++"
ms.assetid: 2d09c7ec-0f16-458e-83ed-7225a1b9221e
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 4
---
# Platform::StringReference 클래스
최저의 복사 작업으로 `Platform::String^` 입력 매개 변수의 문자열 데이터를 다른 메서드로 전달하는 데 사용할 수 있는 최적화 형식입니다.  
  
## 구문  
  
```cpp  
class StringReference  
```  
  
## 설명  
  
## 멤버  
  
### Public 생성자  
  
|이름|설명|  
|--------|--------|  
|[StringReference::StringReference 생성자](../cppcx/stringreference-stringreference-constructor.md)|`StringReference` 인스턴스를 만드는 두 개의 생성자입니다.|  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[StringReference::Data 메서드](../cppcx/stringreference-data-method.md)|문자열 데이터를 char16 값의 배열로 반환합니다.|  
|[StringReference::Length 메서드](../cppcx/stringreference-length-method.md)|문자열의 문자 수를 반환합니다.|  
|[StringReference::GetHSTRING 메서드](../cppcx/stringreference-gethstring-method.md)|문자열 데이터를 HSTRING으로 반환합니다.|  
|[StringReference::GetString 메서드](../cppcx/stringreference-getstring-method.md)|문자열 데이터를 `Platform::String^`로 반환합니다.|  
  
### Public 연산자  
  
|이름|설명|  
|--------|--------|  
|`StringReference::operator=`|새 `StringReference` 인스턴스에 `StringReference`를 할당합니다.|  
|`StringReference::operator()`|`StringReference`를 `Platform::String^`로 변환합니다.|  
  
## 요구 사항  
 **지원되는 최소 클라이언트:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **지원되는 최소 서버:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **네임스페이스:** Platform  
  
 **헤더:** vccorlib.h  
  
## 참고 항목  
 [Platform::StringReference Class](../cppcx/platform-stringreference-class.md)