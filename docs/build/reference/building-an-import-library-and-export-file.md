---
title: "가져오기 라이브러리 및 내보내기 파일 빌드 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLibrarianTool.ModuleDefinitionFile"
  - "VC.Project.VCLibrarianTool.ExportNamedFunctions"
  - "VC.Project.VCLibrarianTool.GenerateDebug"
  - "VC.Project.VCLibrarianTool.ForceSymbolReferences"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".lib 파일"
  - "/DEF 라이브러리 관리자 옵션"
  - "/EXPORT 라이브러리 관리자 옵션"
  - "/INCLUDE 라이브러리 관리자 옵션"
  - "/OUT 라이브러리 관리자 옵션"
  - "DEF 라이브러리 관리자 옵션"
  - "-DEF 라이브러리 관리자 옵션"
  - "EXP 파일"
  - "EXPORT 라이브러리 관리자 옵션"
  - "-EXPORT 라이브러리 관리자 옵션"
  - "데이터 내보내기"
  - "데이터 내보내기, 내보내기(.exp) 파일"
  - "가져오기 라이브러리, 빌드"
  - "INCLUDE 라이브러리 관리자 옵션"
  - "-INCLUDE 라이브러리 관리자 옵션"
  - "OUT 라이브러리 관리자 옵션"
  - "-OUT 라이브러리 관리자 옵션"
ms.assetid: 2fe4f30a-1dd6-4b05-84b5-0752e1dee354
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 가져오기 라이브러리 및 내보내기 파일 빌드
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

가져오기 라이브러리 및 내보내기 파일을 빌드하려면 다음 구문을 사용합니다.  
  
```  
LIB /DEF[:deffile] [options] [objfiles] [libraries]  
```  
  
 \/DEF가 지정된 경우 LIB는 LIB 명령에 전달된 내보내기 사양을 기초로 출력 파일을 만듭니다.  내보내기를 지정하는 데는 다음과 같은 세 가지 방법을 사용합니다\(권장 순서에 따라 나열\).  
  
1.  *objfiles* 또는 *libraries* 중 하나에서의 **\_\_declspec\(dllexport\)** 정의  
  
2.  LIB 명령줄의 \/EXPORT:*name* 사양  
  
3.  `deffile`의 **EXPORTS** 문에서의 정의  
  
 이 방법들은 모두 내보내는 프로그램에 링크할 때 내보내기를 지정하는 데 사용하는 동일한 방법이며,  프로그램에서는 둘 이상의 방법을 사용할 수 있습니다.  LINK 명령에서와 마찬가지로 LIB 명령의 일부\(여러 개의 *objfiles* 또는 \/EXPORT 사양 등\)를 해당 LIB 명령의 명령 파일에서 지정할 수 있습니다.  
  
 다음 옵션은 가져오기 라이브러리 및 내보내기 파일을 빌드하는 데 적용됩니다.  
  
 \/OUT:*import*  
 만들려는 *import* 라이브러리의 기본 출력 파일 이름을 재정의합니다.  \/OUT이 지정되지 않은 경우의 기본 이름은 해당 LIB 명령에 있는 첫 번째 개체 파일 또는 라이브러리의 기본 이름과 .lib 확장명을 사용하여 만들어집니다.  내보내기 파일에는 가져오기 라이브러리와 같은 기본 이름 및 .exp 확장명이 지정됩니다.  
  
 \/EXPORT:*entryname*\[\=*internalname*\]\[,@`ordinal`\[,**NONAME**\]\]\[,**DATA**\]  
 다른 프로그램이 함수를 호출할 수 있도록 프로그램에서 해당 함수를 내보냅니다.  **DATA** 키워드를 사용하여 데이터를 내보낼 수도 있습니다.  내보내기는 대개 DLL에서 정의됩니다.  
  
 *entryname*은 호출 프로그램이 사용할 함수 또는 데이터 항목 이름입니다.  선택적으로, 정의하는 프로그램에 알려진 함수로서 *internalname*을 지정할 수 있습니다. 기본적으로 *internalname*은 *entryname*과 같습니다.  `ordinal`은 내보내기 테이블로 1부터 65,535까지의 인덱스를 지정합니다. 사용자가 `ordinal`을 지정하지 않는 경우에는 LIB에서 이 값을 할당합니다.  **NONAME** 키워드는 함수를 *entryname*이 없는 서수로만 내보냅니다.  **DATA** 키워드는 데이터 전용 개체를 내보내는 데 사용됩니다.  
  
 \/INCLUDE:`symbol`  
 지정된 기호를 기호 테이블에 추가합니다.  이 옵션은 기본적으로 포함되지 않는 라이브러리 개체를 사용하도록 강제로 지정하는 데 유용합니다.  
  
 .dll을 만들기 전에 준비 단계에서 가져오기 라이브러리를 만드는 경우 가져오기 라이브러리를 빌드할 때 전달한 것과 동일한 개체 파일 집합을 .dll을 빌드할 때도 전달해야 합니다.  
  
## 참고 항목  
 [가져오기 라이브러리 및 내보내기 파일을 사용한 작업](../../build/reference/working-with-import-libraries-and-export-files.md)