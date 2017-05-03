---
title: "연산자 Type^ | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
ms.assetid: b24ffc83-0780-4f9a-8ee0-f5725db339d1
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 4
---
# 연산자 Type^
[Windows::UI::Xaml::Interop::TypeName](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.interop.typename.aspx)을 `Platform::Type`으로 변환할 수 있습니다.  
  
## 구문  
  
```cpp  
Operator Type^(Windows::UI::Xaml::Interop::TypeName typeName)  
```  
  
## 반환 값  
 [Windows::UI::Xaml::Interop::TypeName](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.interop.typename.aspx)이 제공되면 `Platform::Type`을 반환합니다.  
  
## 설명  
 `TypeName`은 형식 정보를 나타내기 위한 언어 중립 Windows 런타임 구조체입니다.[Platform::Type](../cppcx/platform-type-class.md)은 C\+\+에서만 사용되며 ABI\(응용 프로그램 이진 인터페이스\) 전반에서 전달될 수 없습니다. 다음은 [Navigate](http://msdn.microsoft.com/library/windows/apps/hh702394.aspx) 함수에서 `TypeName`을 사용하는 한 가지 방법입니다.  
  
```  
rootFrame->Navigate(TypeName(MainPage::typeid), e->Arguments);  
```  
  
## 예제  
 다음 예제에서는 `TypeName`과 `Type` 간을 변환하는 방법을 보여 줍니다.  
  
```  
  
// Convert from Type to TypeName TypeName tn = TypeName(MainPage::typeid); // Convert back from TypeName to Type Type^ tx2 = (Type^)(tn);  
  
```  
  
## 해당 .NET Framework 항목  
 .NET Framework는 `TypeName` 프로젝트를 [System.Type](assetId:///System.Type?qualifyHint=False&amp;autoUpgrade=True)으로 프로그래밍합니다.  
  
## 요구 사항  
  
## 참고 항목  
 [연산자 Windows::UI::Xaml::Interop::TypeName](../cppcx/operator-subtractwindows-ui-xaml-interop-typename.md)   
 [Platform::Type 클래스](../cppcx/platform-type-class.md)