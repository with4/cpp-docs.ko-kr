---
title: "링커 도구 오류 LNK1123 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK1123"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1123"
ms.assetid: fe47af69-0f42-4792-9133-541192cd8514
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# 링커 도구 오류 LNK1123
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

COFF로 변환하는 동안 오류가 발생했습니다. 파일이 잘못되거나 손상되었습니다.  
  
 입력 파일의 형식은 COFF\(Common Object File Format\)여야 합니다.  입력 파일이 COFF가 아니면 링커에서는 자동으로 32비트 OMF 개체를 COFF로 변환하려고 하거나 CVTRES.EXE를 실행하여 리소스 파일을 변환하려고 합니다.  이 메시지는 링커가 파일을 변환할 수 없음을 나타냅니다.  이 오류는 Visual Studio, Windows 개발 키트 또는 .NET Framework의 다른 설치에서 호환되지 않는 CVTRES.EXE 버전을 사용하려는 경우 발생할 수도 있습니다.  
  
> [!NOTE]
>  이전 버전의 Visual Studio를 실행 중이면 자동 변환이 지원되지 않을 수 있습니다.  
  
### 이 문제를 해결하려면  
  
-   사용 중인 Visual Studio 버전에 모든 서비스 팩과 업데이트를 적용합니다.  특히 Visual Studio 2010의 경우에는 이 작업을 반드시 수행해야 합니다.  
  
-   증분 링크를 사용하지 않도록 설정하고 빌드합니다.  메뉴 모음에서 **프로젝트** 메뉴에서 **속성**을 선택합니다.  **속성 페이지** 대화 상자에서 **구성 속성**, **링커**를 확장합니다.  **증분 링크 사용** 값을 **아니요**로 변경합니다.  
  
-   PATH 환경 변수에서 처음으로 찾은 CVTRES.EXE 버전이 빌드 도구의 버전 또는 프로젝트에서 사용하는 플랫폼 도구 집합의 버전과 일치하는지 확인합니다.  
  
-   매니페스트 포함 옵션을 해제합니다.  메뉴 모음에서 **프로젝트** 메뉴에서 **속성**을 선택합니다.  **속성 페이지** 대화 상자에서 **구성 속성**, **매니페스트 도구**, **입력 및 출력**을 확장합니다.  **매니페스트 포함**의 값을 **아니요**로 변경합니다.  
  
-   파일 형식이 올바른지 확인합니다.  예를 들어 OMF 개체가 16비트가 아니라 32비트인지 확인합니다.  자세한 내용은 [링커 입력 파일로 사용하는 .Obj 파일](../../build/reference/dot-obj-files-as-linker-input.md) 및 [Microsoft PE 및 COFF 사양](http://go.microsoft.com/fwlink/p/?LinkId=93292)\(영문\)을 참조하세요.  
  
-   파일이 손상되지 않았는지 확인합니다.  필요한 경우 다시 빌드합니다.  
  
## 참고 항목  
 [링커 입력 파일로 사용하는 .Obj 파일](../../build/reference/dot-obj-files-as-linker-input.md)   
 [EDITBIN 참조](../../build/reference/editbin-reference.md)   
 [DUMPBIN 참조](../../build/reference/dumpbin-reference.md)