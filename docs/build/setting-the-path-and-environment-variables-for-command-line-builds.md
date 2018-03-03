---
title: "명령줄 빌드에 맞는 경로 및 환경 변수 설정 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: get-started-article
f1_keywords:
- include
- Lib
- Path
dev_langs:
- C++
helpviewer_keywords:
- environment variables [C++]
- VCVARS32.bat file
- cl.exe compiler [C++], environment variables
- LINK tool [C++], environment variables
- PATH reserved word
- INCLUDE reserved word
- LINK tool [C++], path
- LIB environment variable
- compiling source code [C++], from command line
- environment variables [C++], CL compiler
ms.assetid: 99389528-deb5-43b9-b99a-03c8773ebaf4
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 76fa1a14b4fd60f249ab015f6618e386bda7c86f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="set-the-path-and-environment-variables-for-command-line-builds"></a>명령줄 빌드에 맞는 경로 및 환경 변수 설정

Visual c + + 명령줄 빌드 도구 설치 및 빌드 구성에 대 한 사용자 지정 된 여러 환경 변수가 필요 합니다. C + + 작업 부하를 설치 하면는 [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] 설치 관리자를 만들므로 사용자 지정 된 명령 파일이 나 필요한 환경 변수를 설정 하는 배치 파일입니다. 다음 설치 관리자 이러한 명령 파일을 사용 하 여 개발자 명령 프롬프트 창을 열려면 Windows 시작 메뉴에 대 한 바로 가기를 만들 수 있습니다. 특정 환경 변수를 설정 하는 이러한 바로 가기를 빌드 구성입니다. 명령줄 도구를 사용 하려는 경우 이러한 바로 가기 중 하나를 실행 하거나 일반 명령 프롬프트 창을 열고 하 고 사용자 지정 명령 파일을 직접 빌드 구성 환경 설정 중 하나를 실행할 수 있습니다. 자세한 내용은 참조 [C/c + + 코드를 명령줄에서 빌드](building-on-the-command-line.md)합니다.  
  
Visual c + + 명령줄 도구는 PATH, TMP, INCLUDE, LIB 및 LIBPATH 환경 변수를 사용 하 여 및 설치 된 도구, 플랫폼 및 Sdk에만 다른 환경 변수를 사용할 수도 있습니다. 간단한도 [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] 설치 20 개 이상의 환경 변수를 설정할 수 있습니다. 이러한 환경 변수 값 설치 및 빌드 구성 선택에 따라 다릅니다 제품 업데이트 또는 업그레이드로 변경할 수 있으므로 좋습니다 개발자 명령 프롬프트 바로 가기를 또는 중 하나를 사용 하는 명령 파일을 설정 하는 대신 Windows 환경에서 설정, 사용자 지정 합니다. 

개발자 명령 프롬프트 바로 가기를 설정한는 환경 변수를 보려면 SET 명령을 사용할 수 있습니다. 일반 명령 프롬프트 창을 열고 하 고 기준에 대해 SET 명령의 출력을 캡처하십시오. 개발자 명령 프롬프트 창을 열고 하 고 비교를 위해 SET 명령의 출력을 캡처하십시오. Visual Studio IDE에 내장 된 것과 같은 비교 도구는 환경 변수를 비교 하 고 개발자 명령 프롬프트에서 설정 된 것을 확인할 유용할 수 있습니다. 컴파일러와 링커에서 사용 하는 특정 환경 변수에 대 한 정보를 참조 하십시오. [CL 환경 변수](../build/reference/cl-environment-variables.md) 및 [LINK 환경 변수](../build/reference/link-environment-variables.md)합니다.  
  
> [!NOTE]
>  여러 명령줄 도구 또는 도구 옵션에는 관리자 권한이 필요할 수 있습니다. 사용 하 여 개발자 명령 프롬프트 창을 열면 권장 있습니다를 사용 하 여 사용 권한 문제를 설정한 경우는 **관리자 권한으로 실행** 옵션입니다. Windows 10에서 명령 프롬프트 창에 대 한 바로 가기 메뉴를 열려면 마우스 오른쪽 단추로 클릭 한 다음 선택 **자세한**, **관리자 권한으로 실행**합니다.  
  
## <a name="see-also"></a>참고 항목  

[C/c + + 코드를 명령줄에서 빌드](../build/building-on-the-command-line.md)   
[연결](../build/reference/linking.md)   
[링커 옵션](../build/reference/linker-options.md)   
[C/c + + 프로그램 컴파일](../build/reference/compiling-a-c-cpp-program.md)   
[컴파일러 옵션](../build/reference/compiler-options.md)