---
title: "네임스페이스 및 형식 표시 유형(C++/CX) | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: cbc01a3a-3b69-4ded-9c42-ecbf0fd0a00e
caps.latest.revision: 13
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 13
---
# 네임스페이스 및 형식 표시 유형(C++/CX)
네임스페이스는 관련된 기능을 가진 형식을 그룹화하고 라이브러리의 이름 충돌을 방지하기 위한 표준 C\+\+ 구조입니다.[!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 형식 시스템에서는 사용자의 고유 코드에 있는 public 형식을 비롯한 모든 public [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 형식이 네임스페이스 범위에서 네임스페이스에 선언되어야 합니다. 전역 범위에서 선언되거나 다른 클래스 안에 중첩된 public 형식은 컴파일 타임 오류를 발생시킵니다.  
  
 .winmd 파일은 루트 네임스페이스와 이름이 같아야 합니다. 예를 들어 이름이 A.B.C.MyClass인 클래스는 이름이 A.winmd, A.B.winmd 또는 A.B.C.winmd인 메타데이터 파일에 정의된 경우에만 인스턴스화될 수 있습니다. 실행 파일의 이름은 .winmd 파일 이름과 일치하지 않아도 됩니다.  
  
## 형식 표시 유형  
 네임스페이스에서 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 형식은 표준 C\+\+ 형식과 달리 private 또는 public 액세스 가능성을 갖고 있습니다. 기본적으로 액세스 가능성은 private입니다. public 형식만 메타데이터에 표시되므로 C\+\+ 이외의 언어로 작성될 수 있는 응용 프로그램과 구성 요소에서 사용될 수 있습니다. 일반적으로 표시되는 형식은 .NET 언어 또는 JavaScript에서 지원되지 않는 C\+\+ 관련 개념을 노출할 수 없기 때문에 표시되는 형식에 대한 규칙은 표시되지 않는 형식에 대한 규칙보다 제한적입니다.  
  
> [!NOTE]
>  메타데이터는 .NET 언어 및 JavaScript에서 런타임에만 사용됩니다. C\+\+ 응용 프로그램 또는 구성 요소가 다른 C\+\+ 응용 프로그램 또는 구성 요소\(모두 C\+\+로 작성된 Windows 구성 요소 포함\)와 통신 중인 경우 메타데이터의 런타임 사용이 필요하지 않습니다.  
  
## 멤버 액세스 가능성 및 표시 유형  
 private ref 클래스, 인터페이스 또는 대리자에서는 public 액세스 가능성이 있는 멤버를 비롯한 모든 멤버가 메타데이터로 내보내지지 않습니다. public ref 클래스에서는 소스 코드에서의 액세스 가능성과 독립적으로 메타데이터에서 멤버의 표시 유형을 제어할 수 있습니다. 표준 C\+\+에서와 마찬가지로 최소 권한 원칙을 적용합니다. 메타데이터에서 멤버가 절대적으로 표시되어야 하는 경우가 아니면 표시되게 하지 마세요.  
  
 다음 액세스 한정자를 사용하여 메타데이터 표시 유형과 소스 코드 액세스 가능성을 제어할 수 있습니다.  
  
||||  
|-|-|-|  
|한정자|의미|메타데이터로 내보낼지 여부|  
|private|기본 액세스 가능성입니다. 표준 C\+\+에서와 동일한 의미를 갖습니다.|아니요|  
|protected|응용 프로그램 또는 구성 요소와 메타데이터에서 표준 C\+\+에서와 동일한 의미를 갖습니다.|예|  
|public|표준 C\+\+에서와 동일한 의미를 갖습니다.|예|  
|`public protected` 또는 `protected public`|액세스 가능성이 메타데이터에서는 protected이고 응용 프로그램 또는 구성 요소에서는 public입니다.|예|  
|`protected private` 또는 `private protected`|메타데이터에서는 표시되지 않고 응용 프로그램 또는 구성 요소에서는 액세스 가능성이 protected입니다.||  
|`internal` 또는 `private public`|멤버가 응용 프로그램 또는 구성 요소에서는 public이지만 메타데이터에서는 표시되지 않습니다.|아니요|  
  
## [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 네임스페이스  
 Windows API는 Windows::\* 네임스페이스에 선언된 형식으로 구성됩니다. 이러한 네임스페이스는 Windows용으로 예약되어 있으며 해당 네임스페이스에는 형식을 추가할 수 없습니다.**개체 브라우저**의 windows.winmd 파일에서 이러한 네임스페이스를 볼 수 있습니다. 이러한 네임스페이스에 대한 설명은 [Windows API](http://msdn.microsoft.com/library/windows/apps/br211377)를 참조하세요.  
  
## [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] 네임스페이스  
 [!INCLUDE[cppwrt](../cppcx/includes/cppwrt-md.md)]\([!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]\)은 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 형식 시스템을 투영하기 위해 이러한 네임스페이스에 특정 형식을 정의합니다.  
  
|||  
|-|-|  
|**네임스페이스**|**설명**|  
|default|기본 제공되는 숫자 및 char16 형식을 포함하고 있습니다. 이러한 형식은 모든 네임스페이스에서 범위 내에 있는 것으로 간주되므로 `using` 문이 필요하지 않습니다.|  
|플랫폼|[!INCLUDE[wrt](../cppcx/includes/wrt-md.md)], `Array<T>`, `String` 및 `Guid`과 같은 `Boolean` 형식에 해당하는 공용 형식을 주로 포함합니다.`Platform::Agile<T>` 및 `Platform::Box<T>`와 같은 특수한 도우미 형식도 포함합니다.|  
|Platform::Collections|[!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 컬렉션 인터페이스 `IVector`, `IMap` 등을 구현하는 구체적 컬렉션 클래스를 포함합니다. 이러한 형식은 platform.winmd가 아니라 헤더 파일인 collection.h에 정의되어 있습니다.|  
|Platform::Details|컴파일러가 사용하며 공용으로는 사용되지 않는 형식을 포함합니다.|  
  
## 참고 항목  
 [형식 시스템\(C\+\+\/CX\)](../cppcx/type-system-c-cx.md)