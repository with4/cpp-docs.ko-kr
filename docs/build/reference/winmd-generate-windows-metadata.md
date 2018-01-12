---
title: "-WINMD (Windows 메타 데이터 생성) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VC.Project.VCLinkerTool.GenerateWindowsMetadata
dev_langs: C++
ms.assetid: bcfb4901-411e-4c9e-9f78-23028b6e5fcc
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 903ab6875457aa8c069c47a2be7f8ff1f5c884a9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="winmd-generate-windows-metadata"></a>/WINMD(Windows 메타데이터 생성)
Windows 런타임 메타데이터(.winmd) 파일을 생성할 수 있게 해줍니다.  
  
```  
/WINMD[:{NO|ONLY}]  
```  
  
## <a name="remarks"></a>설명  
 /WINMD  
 [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] 응용 프로그램의 기본 설정입니다. 링커가 바이너리 실행 파일 및 .winmd 메타데이터 파일을 모두 생성합니다.  
  
 /WINMD:NO  
 링커가 바이너리 실행 파일만 생성하고 .winmd 파일은 생성하지 않습니다.  
  
 /WINMD:ONLY  
 링커가 .winmd 파일만 생성하고 바이너리 실행 파일은 생성하지 않습니다.  
  
 기본적으로 출력 파일 이름의 형식은 `binaryname`.winmd입니다. 다른 파일 이름을 지정 하려면는 [/WINMDFILE](../../build/reference/winmdfile-specify-winmd-file.md) 옵션입니다.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.  
  
2.  선택 된 **링커** 폴더입니다.  
  
3.  선택 된 **Windows 메타 데이터** 속성 페이지.  
  
4.  에 **일반 Windows 메타 데이터** 드롭다운 목록 상자에서 원하는 옵션을 선택 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)