---
title: "Platform::Object 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Object"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Object 클래스"
ms.assetid: 709e84a8-0bff-471b-bc14-63e424080b5a
caps.latest.revision: 9
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 9
---
# Platform::Object 클래스
Windows Store 앱의 ref 클래스 및 ref 구조체에 대해 일반적인 동작을 제공합니다. 모든 ref 클래스 및 ref 구조체 인스턴스는 Platform::Object^로 암시적으로 변환될 수 있고 해당하는 가상 ToString 메서드를 재정의할 수 있습니다.  
  
## 구문  
  
```scr  
public ref class Object : Object  
```  
  
## 멤버  
  
### Public 생성자  
  
|이름|설명|  
|--------|--------|  
|[Object::Object 생성자](../cppcx/object-object-constructor.md)|Object 클래스의 새 인스턴스를 초기화합니다.|  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[Object::Equals 메서드](../cppcx/object-equals-method.md)|지정한 개체와 현재 개체가 같은지 여부를 확인합니다.|  
|[Object::GetHashCode 메서드](../cppcx/object-gethashcode-method.md)|이 인스턴스의 해시 코드를 반환합니다.|  
|[Object::ReferenceEquals 메서드](../cppcx/object-referenceequals-method.md)|지정한 Object 인스턴스가 동일한지 여부를 확인합니다.|  
|[ToString 메서드](../cppcx/object-tostring-method-c-cx.md)|현재 개체를 나타내는 문자열을 반환합니다. 재정의될 수 있습니다.|  
|[GetType 메서드](../cppcx/object-gettype-method.md)|현재 인스턴스를 설명하는 [Platform::Type](../cppcx/platform-type-class.md)을 가져옵니다.|  
  
## 상속 계층  
 `Object`  
  
 `Object`  
  
## 요구 사항  
 **헤더:** vccorlib.h  
  
 **네임스페이스:** Platform  
  
## 참고 항목  
 [\(NOTINBUILD\) Platform 네임스페이스](http://msdn.microsoft.com/ko-kr/f3ce3eab-028c-4204-ba9f-9ab8af17c8c4)