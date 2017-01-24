---
title: "Override 지정자(C++ 구성 요소 확장) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "override 지정자, Visual C++"
  - "override 지정자"
ms.assetid: 155bbf6f-4722-4654-afb1-9cb52af799fb
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Override 지정자(C++ 구성 요소 확장)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

*재정의 지정자*는 상속된 형식과 상속된 형식의 멤버가 파생 형식에서 동작하는 방법을 수정합니다.  
  
## 모든 런타임  
 **설명**  
  
 재정의 지정자에 대한 자세한 내용은 다음을 참조하십시오.  
  
-   [abstract](../windows/abstract-cpp-component-extensions.md)  
  
-   [new\(vtable의 new 슬롯\)](../windows/new-new-slot-in-vtable-cpp-component-extensions.md)  
  
-   [override](../windows/override-cpp-component-extensions.md)  
  
-   [sealed](../windows/sealed-cpp-component-extensions.md)  
  
-   [재정의 지정자 및 네이티브 컴파일](../dotnet/how-to-declare-override-specifiers-in-native-compilations-cpp-cli.md)  
  
 재정의 지정자로 사용되지 않는 형식 선언에서는 `abstract` 및 `sealed`도 유효합니다.  
  
 기본 클래스 함수의 명시적 재정의에 대한 자세한 내용은 [명시적 재정의](../windows/explicit-overrides-cpp-component-extensions.md)를 참조하십시오.  
  
## Windows 런타임\(Windows Runtime\)  
 \(이 언어 기능에는 Windows 런타임에만 적용되는 설명이 없습니다.\)  
  
### 요구 사항  
 컴파일러 옵션: **\/ZW**  
  
## 공용 언어 런타임  
 \(이 언어 기능에는 공용 언어 런타임에만 적용되는 설명이 없습니다.\)  
  
### 요구 사항  
 컴파일러 옵션: **\/clr**  
  
## 참고 항목  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)