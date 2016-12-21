---
title: "상속(C++) | Microsoft Docs"
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
  - "클래스[C++], 파생"
  - "파생 클래스"
  - "파생 클래스, 파생 클래스 정보"
ms.assetid: 3534ca19-d9ed-4a40-be1b-b921ad0e6956
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 상속(C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 단원에서는 파생 클래스를 사용하여 확장 가능한 프로그램을 생성하는 방법을 설명합니다.  
  
## 개요  
 새 클래스는 "상속" 메커니즘을 사용하여 기존 클래스에서 파생될 수 있습니다\([단일 상속](../cpp/single-inheritance.md)으로 시작하는 정보 참조\).  파생에 사용되는 클래스를 특정 파생 클래스의 "기본 클래스"라고 합니다.  파생 클래스는 다음 구문을 사용하여 선언됩니다.  
  
```  
 class Derived : [virtual] [access-specifier] Base  
{  
   // member list  
};  
 class Derived : [virtual] [access-specifier] Base1,  
 [virtual] [access-specifier] Base2, . . .  
{  
   // member list  
};  
```  
  
 클래스에 대한 태그\(이름\) 뒤에 콜론과 기본 사양 목록이 나타납니다.  그렇게 명명된 기본 클래스는 이전에 선언되어 있어야 합니다.  기본 사양은 **public**, `protected` 또는 `private` 키워드 중 하나인 액세스 지정자를 포함할 수 있습니다.  이러한 액세스 지정자는 기본 클래스 이름 앞에 나타나고 해당 기본 클래스에만 적용됩니다.  이러한 지정자는 기본 클래스의 멤버를 사용할 수 있는 파생 클래스의 권한을 제어합니다.  기본 클래스 멤버 액세스에 대한 자세한 내용은 [멤버 액세스 제어](../cpp/member-access-control-cpp.md)를 참조하십시오.  액세스 지정자를 생략할 경우 해당 기본 클래스 멤버에 대한 액세스가 `private`으로 간주됩니다.  기본 사양은 가상 상속을 나타내기 위해 **virtual** 키워드를 포함할 수 있습니다.  이 키워드는 액세스 지정자\(있는 경우\) 앞이나 뒤에 나타날 수 있습니다.  가상 상속을 사용하는 경우 기본 클래스를 가상 기본 클래스라고 합니다.  자세한 내용은 [가상 기본 클래스](../misc/virtual-base-classes.md)를 참조하십시오.  
  
 여러 기본 클래스를 쉼표로 구분하여 지정할 수 있습니다.  단일 기본 클래스를 지정하는 경우 상속 모델은 [단일 상속](../cpp/single-inheritance.md)이고 둘 이상의 기본 클래스를 지정하는 경우에는 상속 모델을 [다중 상속](http://msdn.microsoft.com/ko-kr/3b74185e-2beb-4e29-8684-441e51d2a2ca)이라고 합니다.  
  
 주제는 다음과 같습니다.  
  
-   [단일 상속](../cpp/single-inheritance.md)  
  
-   [다중 상속](http://msdn.microsoft.com/ko-kr/3b74185e-2beb-4e29-8684-441e51d2a2ca)  
  
-   [다중 기본 클래스](../cpp/multiple-base-classes.md)  
  
-   [가상 기본 클래스](../misc/virtual-base-classes.md)  
  
-   [가상 함수](../cpp/virtual-functions.md)  
  
-   [명시적 재정의](../cpp/explicit-overrides-cpp.md)  
  
-   [추상 클래스](../cpp/abstract-classes-cpp.md)  
  
-   [범위 규칙 요약](../cpp/summary-of-scope-rules.md)  
  
 [\_\_super](../cpp/super.md) 및 [\_\_interface](../cpp/interface.md) 키워드는 이 단원에서 다룹니다.  
  
## 참고 항목  
 [C\+\+ 언어 참조](../cpp/cpp-language-reference.md)