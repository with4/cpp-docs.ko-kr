---
title: "LINK 출력 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "link"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".ilk 파일"
  - "DLL[C++], 링커 출력으로 사용"
  - "실행 파일[C++], 링커 출력으로 사용"
  - "파일[C++], LINK"
  - "ILK 파일"
  - "가져오기 라이브러리[C++], 만들기"
  - "LINK 도구[C++], 맵 파일"
  - "LINK 도구[C++], 출력"
  - "링커[C++], 출력 파일"
  - "맵 파일[C++]"
  - "맵 파일[C++], LINK 출력"
  - "출력 파일[C++], 링커"
ms.assetid: a98b557c-1947-447a-be1f-616fb45a9580
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# LINK 출력
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

링크 출력에는 .exe 파일, DLL, 맵 파일, 메시지가 있습니다.  
  
##  <a name="_core_output_files"></a> 출력 파일  
 LINK의 기본 출력 파일은 .exe 파일입니다.  [\/DLL](../../build/reference/dll-build-a-dll.md) 옵션을 지정한 경우 LINK에서는 .dll 파일을 빌드합니다.  출력 파일 이름은 [\/OUT\(출력 파일 이름\)](../../build/reference/out-output-file-name.md) 옵션을 사용하여 사용자가 지정할 수 있습니다.  
  
 증분 모드에 있는 경우 LINK에서는 .ilk 파일을 만들어 프로그램의 후속 증분 빌드에 대한 상태 정보를 보관합니다.  .ilk 파일에 대한 자세한 내용은 [.ilk 파일](../../build/reference/dot-ilk-files-as-linker-input.md)을 참조하십시오.  증분 링크에 대한 자세한 내용은 [\/INCREMENTAL\(증분 링크\)](../../build/reference/incremental-link-incrementally.md) 옵션을 참조하십시오.  
  
 LINK에서는 내보내기\(대개 DLL\)가 포함된 프로그램을 만들 때 해당 빌드에 .exp 파일이 사용되지 않았으면 .lib 파일도 빌드합니다.  가져오기 라이브러리 파일 이름은 [\/IMPLIB](../../build/reference/implib-name-import-library.md) 옵션을 사용하여 사용자가 지정할 수 있습니다.  
  
 [맵 파일 생성\(\/MAP\)](../../build/reference/map-generate-mapfile.md) 옵션을 지정한 경우 LINK에서는 맵 파일을 만듭니다.  
  
 [디버그 정보 생성\(\/DEBUG\)](../../build/reference/debug-generate-debug-info.md) 옵션을 지정한 경우 LINK에서는 PDB를 만들어 프로그램에 대한 디버깅 정보를 보관합니다.  
  
##  <a name="_core_other_output"></a> 기타 출력  
 다른 명령줄 입력 없이 `link`만 입력하면 옵션을 요약한 LINK의 사용법 문이 표시됩니다.  
  
 LINK에서는[\/NOLOGO\(시작 배너 표시 안 함\)](../../build/reference/nologo-suppress-startup-banner-linker.md) 옵션이 사용되지 않은 경우 저작권 및 버전 관련 메시지를 표시하고 명령 파일 입력을 에코합니다.  
  
 [\/VERBOSE\(진행 메시지 표시\)](../../build/reference/verbose-print-progress-messages.md) 옵션을 사용하면 빌드에 관한 추가 정보를 표시할 수 있습니다.  
  
 LINK에서는 오류 및 경고 메시지를 LNK*nnnn* 형식으로 표시합니다.  이 오류 접두사와 범위를 나타내는 숫자는 LIB, DUMPBIN, EDITBIN에서도 사용됩니다.  
  
## 참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)