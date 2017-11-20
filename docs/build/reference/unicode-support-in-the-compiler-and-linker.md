---
title: "컴파일러 및 링커에서의 유니코드 지원 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.UseUnicodeResponseFiles
- VC.Project.VCLibrarianTool.UseUnicodeResponseFiles
- VC.Project.VCCLCompilerTool.UseUnicodeResponseFiles
- VC.Project.VCXDCMakeTool.UseUnicodeResponseFiles
dev_langs: C++
helpviewer_keywords: Unicode, Visual C++
ms.assetid: acc1d322-56b9-4696-a30e-2af891a4e288
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 15fefc4cc44edfd67bd8ba89ab68c6965c8639a6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="unicode-support-in-the-compiler-and-linker"></a>컴파일러 및 링커에서의 유니코드 지원
이 항목에서는 Visual c + + 빌드 도구에서 지 원하는 유니코드에 설명 합니다.  
  
 파일 이름  
 명령줄에서 또는 컴파일러 지시문에 지정 된 파일 이름 (예: #include) 이제 유니코드 문자를 포함할 수 있습니다.  
  
 소스 코드 파일  
 유니코드 문자는 식별자, 매크로, 문자열 및 문자 리터럴, 한 주석에서 이제 지원 됩니다.  유니버설 문자 이름은 사용할 수 있습니다.  
  
 다음 인코딩에서는 소스 코드 파일에 유니코드를 입력할 수 있습니다.  
  
-   U t F-16 little endian 바이트 순서 표시 (BOM) 유무  
  
-   Utf-16 big endian BOM 유무  
  
-   U t F-8 bom  
  
 출력  
 컴파일하는 동안 컴파일러 진단 u t F-16으로 콘솔에 출력합니다.  콘솔에 표시 될 수 있는 문자는 콘솔 창 속성에 따라 달라 집니다.  컴파일러 출력을 파일로 리디렉션되의 현재 ANSI 콘솔 코드 페이지가 있는 경우  
  
 링커 지시 파일 및 합니다. DEF 파일  
 응답 파일 및 DEF 파일 바이트 순서 표시 또는 ANSI 중 하나가 u t F-16을 수 있습니다.  이전에 ANSI만 지원 되었습니다.  
  
 .asm 및.cod 덤프  
 .asm 및.cod 덤프 MASM 호환을 위해 기본적으로 ansi에서 됩니다.  /FAu를 사용 하 여 u t F-8을 출력 합니다.  Note /FAs를 지정 하면 소스가 직접 인쇄 됩니다 및 예를 들어 소스 코드는 u t F-8이 고 /FAsu 지정 하지 않은 경우 잘못 된 보일 수 있습니다.  
  
 개발 환경에서 유니코드 파일 이름을 사용 하도록 설정할 수 있습니다 (참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)) 하 고 선택 하 여 적절 한 도구를 선택 하 여는 **유니코드 지시 파일을 사용 하도록 설정** 속성 기본적으로 활성화 되어 있습니다. 이 기본값을 변경할 수는 한 가지 이유 유니코드를 지원 하지 않은 컴파일러를 사용 하도록 개발 환경을 수정 하는 경우입니다.  
  
## <a name="see-also"></a>참고 항목  
 [C/c + + 코드를 명령줄에서 빌드](../../build/building-on-the-command-line.md)