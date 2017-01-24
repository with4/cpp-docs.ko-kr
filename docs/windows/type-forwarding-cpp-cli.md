---
title: "Type Forwarding (C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
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
  - "type forwarding, Visual C++"
ms.assetid: ae730b69-0c27-41cc-84e1-3132783866ea
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Type Forwarding (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

*형식 전달* 은 어셈블리 A를 소비하는 클라이언트를 재 컴파일 할 필요가 없도록하는 다른 어셈블리 \(어셈블리 B\)에 1 어셈블리 \(어셈블리 A\)에서 형식을 이동할 수 있습니다  
  
## 모든 플랫폼  
 모든 런타임에서 이 기능은 지원되지 않습니다.  
  
## Windows 런타임\(Windows Runtime\)  
 이 기능은 [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]에서 지원되지 않습니다.  
  
### 요구 사항  
 컴파일러 옵션: **\/ZW**  
  
## 공용 언어 런타임  
 다음 코드 예제에서는 형식 전달을 사용하는 방법을 보여줍니다.  
  
### 구문  
  
```  
#using "new.dll"  
[assembly:TypeForwardedTo(type::typeid)];  
```  
  
### 매개 변수  
 `new`  
 형식 정의를 이동하는 어셈블리입니다.  
  
 `type`  
 정의 가진 다른 어셈블리로 이동하는 형식입니다.  
  
### 설명  
 구성 요소 \(어셈블리\) 제공 및 클라이언트 응용 프로그램에서 사용된 후, 업데이트 된 구성 요소 \(및 필요한 추가 어셈블리\)를 발송하고 다른 어셈블리에 컴포넌트 \(어셈블리\)에서 형식을 이동하는 유형의 전송을 사용 하고있는 클라이언트 응용 프로그램 아직 다시 컴파일하지 않고 작동합니다.  
  
 기존 응용 프로그램에서 참조 된 구성 요소에 대한 전달 형식에서만 작동합니다.  응용 프로그램을 다시 빌드할 때 응용 프로그램에 사용되는 모든 형식에 대한 적절한 어셈블리 참조가 있어야 합니다.  
  
 어셈블리에서 형식 \(형식 A\)에 전달할 때 어셈블리 참조 뿐만아니라 해당 형식의 `TypeForwardedTo`  속성을 추가해야합니다.  참조하는 어셈블리 중 하나를 포함해야 합니다.  
  
-   유형 a의 정의  
  
-   `TypeForwardedTo` 은 어셈블리 참조뿐만 아니라 유형 A에 대한 특성입니다.  
  
 전달될 수 있는 형식의 예는 다음과 같습니다.  
  
-   ref 클래스  
  
-   value 클래스  
  
-   열거형  
  
-   인터페이스  
  
 다음 형식은 전달할 수 없습니다.  
  
-   제네릭 형식  
  
-   네이티브 형식.  
  
-   중첩 형식 \(중첩된 형식에 전달 하려는 경우, 바깥쪽 형식을 전달해야 합니다.\)  
  
 형식을 공용 언어 런타임을 대상으로 하는 모든 언어로 작성된 어셈블리를 전달할 수 있습니다.  
  
 그래서, 만약 A.dll를 형식 정의 \(`ref class MyClass`\)를 포함하는 어셈블리를 빌드하는 데 사용됩니다. 어셈블리 B.dll의 해당 형식의 정의를 이동하기 위해 요구되는 소스 코드 파일 :  
  
1.  B.dll을 빌드하는 데 사용되는 소스 코드 파일에  `MyClass`  형식 정의를 이동합니다.  
  
2.  B.dll 어셈블리 빌드  
  
3.  A.dll를 구축하고 다음과 같이 대체에 사용 된 소스 코드에서 `MyClass` 형식의 정의를 삭제합니다.  
  
    ```  
    #using "B.dll"  
    [assembly:TypeForwardedTo(MyClass::typeid)];  
    ```  
  
4.  A.dll 어셈블리를 빌드합니다.  
  
5.  클라이언트 응용 프로그램을 다시 컴파일하지 않고 A.dll을 사용합니다.  
  
### 요구 사항  
 컴파일러 옵션: **\/clr**