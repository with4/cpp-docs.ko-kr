---
title: '방법: 안정형 c + + 프로젝트 만들기 (C + + /cli CLI) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- verifiable assemblies [C++], creating
- conversions, C++ projects
- Visual C++ projects
ms.assetid: 4ef2cc1a-e3e5-4d67-8d8d-9c614f8ec5d3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: a012e52a8eb825c3ffc6b694c888cef8a174f37e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-verifiable-c-projects-ccli"></a>방법: 안정형 C++ 프로젝트 만들기(C++/CLI)
Visual c + + 응용 프로그램 마법사는 확인할 수 있는 프로젝트를 만들지 않습니다 되지만 프로젝트를 확인할 수 있으려면 변환할 수 있습니다. 이 항목에서는 프로젝트 속성을 설정 하 고 확인할 수 있는 응용 프로그램을 생성 하 여 Visual c + + 프로젝트를 변환할 프로젝트 소스 파일을 수정 하는 방법에 설명 합니다.  
  
## <a name="compiler-and-linker-settings"></a>컴파일러 및 링커 설정  
 기본적으로.NET 프로젝트의 /clr 컴파일러 플래그를 사용 하 고 링커 x86 대상 하드웨어를 구성 합니다. 안정형 코드에 대 한 /clr: safe 플래그를 사용 해야 하 고 네이티브 기계어 명령 대신 MSIL을 생성 하도록 링커에 지시 해야 합니다.  
  
#### <a name="to-change-the-compiler-and-linker-settings"></a>컴파일러 및 링커 설정을 변경 하려면  
  
1.  프로젝트 속성 페이지를 표시 합니다. 자세한 내용은 참조 [프로젝트 속성 작업](../ide/working-with-project-properties.md)합니다.  
  
2.  에 **일반** 페이지는 **구성 속성** 노드를 설정의 **공용 언어 런타임 지원** 속성을 **안전 MSIL 공용 언어 런타임 지원 (/: safe)** 합니다.  
  
3.  에 **고급** 페이지는 **링커** 노드를 설정의 **CLR 이미지 형식을** 속성을 **안전 IL 이미지 강제 (/: safe)** 합니다.  
  
## <a name="removing-native-data-types"></a>네이티브 데이터 형식 제거  
 네이티브 데이터 형식은 실제로 사용 되지 않는 경우에 비안정형 이므로 네이티브 형식이 포함 된 모든 헤더 파일을 제거 해야 합니다.  
  
> [!NOTE]
>  다음 절차는 Windows Forms 응용 프로그램 (.NET) 및 콘솔 응용 프로그램 (.NET) 프로젝트에 적용 됩니다.  
  
#### <a name="to-remove-references-to-native-data-types"></a>네이티브 데이터 형식에 대 한 참조를 제거 하려면  
  
1.  주석 Stdafx.h 파일에 있는 모든 것으로 처리 합니다.  
  
## <a name="configuring-an-entry-point"></a>진입점 구성  
 확인할 수 있는 응용 프로그램에서 C 런타임 라이브러리 (CRT)를 사용할 수 없는 때문에 표준 진입점으로 main 함수를 호출 하는 CRT 의존 수 없습니다. 즉, 링커에 처음 호출할 함수의 이름을 명시적으로 제공 해야 합니다. (이 경우 main ()는 비 CRT 진입점을 나타내기 위해 main () 또는 _tmain 대신 사용 됩니다 하지만이 이름은 임의로 지정 되므로 진입점을 명시적으로 지정 해야 합니다.)  
  
> [!NOTE]
>  다음 절차는 콘솔 응용 프로그램 (.NET) 프로젝트에 적용 합니다.  
  
#### <a name="to-configure-an-entry-point"></a>진입점을 구성 하려면  
  
1.  프로젝트의 주.cpp 파일의 main ()를 _tmain을 변경 합니다.  
  
2.  프로젝트 속성 페이지를 표시 합니다. 자세한 내용은 참조 [프로젝트 속성 작업](../ide/working-with-project-properties.md)합니다.  
  
3.  에 **고급** 페이지는 **링커** 노드를 입력 `Main` 로 **진입점** 속성 값입니다.  
  
## <a name="see-also"></a>참고 항목  
 [순수형 및 안정형 코드(C++/CLI)](../dotnet/pure-and-verifiable-code-cpp-cli.md)