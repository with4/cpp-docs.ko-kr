---
title: "Object::GetType 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Object::GetType"
ms.assetid: f633d71a-ff80-49f9-931d-189c00b1f6c5
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Object::GetType 메서드
개체의 런타임 형식을 설명하는 [Platform::Type](../cppcx/platform-type-class.md) 개체를 반환합니다.  
  
## 구문  
  
```vb  
Object::GetType()  
```  
  
```csharp  
  
```  
  
## 속성 값\/반환 값  
 개체의 런타임 형식을 설명하는 [Platform::Type](../cppcx/platform-type-class.md) 개체입니다.  
  
## 설명  
 정적 [Type::GetTypeCode 메서드](../cppcx/type-gettypecode-method.md)를 사용하여 현재 형식을 나타내는 [Platform::TypeCode 열거형](../cppcx/platform-typecode-enumeration.md) 값을 가져올 수 있습니다. 대부분의 경우 이는 기본 제공 형식에 유용합니다.[Platform::String](../cppcx/platform-string-class.md)을 제외한 모든 ref 클래스에 대한 형식 코드가 개체 \(1\)입니다.  
  
 [Windows::UI::Xaml::Interop::TypeName](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.interop.typename.aspx) 클래스는 Windows API에서 언어와 관계없이 Windows 구성 요소와 앱 간에 형식 정보를 전달하는 방법으로 사용됩니다.[Platform::Type 클래스](../cppcx/platform-type-class.md)에는 `Type`과 `TypeName` 간을 변환하기 위한 연산자가 있습니다.  
  
 [typeid](~/windows/typeid-cpp-component-extensions.md) 연산자를 사용하면 XAML 페이지 간을 탐색할 때 등에 클래스 이름에 대한 `Platform::Type` 개체를 반환할 수 있습니다.  
  
```  
rootFrame->Navigate(TypeName(MainPage::typeid), e->Arguments);  
```  
  
## 참고 항목  
 [Platform::Type 클래스](../cppcx/platform-type-class.md)   
 [Platform 네임스페이스](../cppcx/platform-namespace-c-cx.md)   
 [형식 시스템](../cppcx/type-system-c-cx.md)