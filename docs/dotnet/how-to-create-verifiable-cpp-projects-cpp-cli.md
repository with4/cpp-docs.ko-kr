---
title: "방법: 안정형 C++ 프로젝트 만들기(C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "변환, C++ 프로젝트"
  - "안정형 어셈블리[C++], 만들기"
  - "Visual C++ 프로젝트"
ms.assetid: 4ef2cc1a-e3e5-4d67-8d8d-9c614f8ec5d3
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: 안정형 C++ 프로젝트 만들기(C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+ 응용 프로그램 마법사로 안정형 프로젝트를 만들 수는 없지만 프로젝트를 안정형으로 변환할 수는 있습니다.  이 항목에서는 Visual C\+\+ 프로젝트를 변환하여 안정형 응용 프로그램을 만들 수 있도록 프로젝트 속성을 설정하고 프로젝스 소스 파일을 수정하는 방법에 대해 설명합니다.  
  
## 컴파일러 및 링커 설정  
 기본적으로 .NET 프로젝트에서는 \/clr 컴파일러 플래그를 사용하고 x86 하드웨어를 대상으로 링커를 구성합니다.  안정형 코드의 경우 \/clr:safe 플래그를 사용해야 하고 네이티브 컴퓨터 명령 대신 MSIL을 생성하도록 링커에 직접 지시해야 합니다.  
  
#### 컴파일러 및 링커 설정을 변경하려면  
  
1.  프로젝트 속성 페이지를 표시합니다.  자세한 내용은 [방법: 프로젝트 속성 페이지 열기](../misc/how-to-open-project-property-pages.md)을 참조하십시오.  
  
2.  **구성 속성** 노드 아래의 **일반** 페이지에서 **공용 언어 런타임 지원** 속성을 **안전 MSIL 공용 언어 런타임 지원\(\/clr:safe\)**으로 설정합니다.  
  
3.  **링커** 노드 아래의 **고급** 페이지에서 **CLR 이미지 형식** 속성을 **안전 IL 이미지 강제\(\/CLRIMAGETYPE:SAFE\)**로 설정합니다.  
  
## 네이티브 데이터 형식 제거  
 네이티브 데이터 형식은 비안정형이므로 실제로 사용되지 않더라도 네이티브 형식이 포함된 헤더 파일을 모두 제거해야 합니다.  
  
> [!NOTE]
>  다음 절차는 Windows Forms 응용 프로그램\(.NET\) 및 콘솔 응용 프로그램\(.NET\) 프로젝트에 적용됩니다.  
  
#### 네이티브 데이터 형식에 대한 참조를 제거하려면  
  
1.  Stdafx.h 파일의 내용을 모두 주석 처리합니다.  
  
## 진입점 구성  
 안정형 응용 프로그램에서는 CRT\(C 런타임 라이브러리\)를 사용할 수 없으므로 표준 진입점으로 주 함수를 호출하는 데 CRT를 사용할 수 없습니다.  즉, 처음 호출할 함수의 이름을 명시적으로 링커에 지정해야 합니다. 이 경우 CRT가 아닌 진입점임을 나타내기 위해 main\(\) 또는 \_tmain\(\) 대신 Main\(\)이 사용되었지만 진입점은 명시적으로 지정해야 하므로 이 이름은 임의로 설정할 수 있습니다.  
  
> [!NOTE]
>  다음 절차는 콘솔 응용 프로그램\(.NET\) 프로젝트에 적용됩니다.  
  
#### 진입점을 구성하려면  
  
1.  프로젝트의 주 .cpp 파일에서 \_tmain\(\)을 Main\(\)으로 변경합니다.  
  
2.  프로젝트 속성 페이지를 표시합니다.  자세한 내용은 [방법: 프로젝트 속성 페이지 열기](../misc/how-to-open-project-property-pages.md)을 참조하십시오.  
  
3.  **링커** 노드의 아래에 있는 **고급** 페이지에서 **진입점** 속성 값으로 `Main`을 입력합니다.  
  
## 참고 항목  
 [순수형 및 안정형 코드](../dotnet/pure-and-verifiable-code-cpp-cli.md)