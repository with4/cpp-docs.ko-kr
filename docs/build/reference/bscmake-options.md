---
title: "BSCMAKE 옵션 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCBscMakeTool.OutputFile"
  - "VC.Project.VCBscMakeTool.SuppressStartupBanner"
  - "VC.Project.VCBscMakeTool.PreserveSBR"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/v BSCMAKE 옵션"
  - "Iu BSCMAKE 옵션"
  - "찾아보기 정보 파일(.bsc), 내용"
  - "/Er BSCMAKE 옵션"
  - "NOLOGO BSCMAKE 옵션"
  - "/s BSCMAKE 옵션"
  - "/Ei BSCMAKE 옵션"
  - "/o BSCMAKE 옵션"
  - "/NOLOGO BSCMAKE 옵션"
  - "/Iu BSCMAKE 옵션"
  - "s BSCMAKE 옵션(/s)"
  - "/Em BSCMAKE 옵션"
  - "Em BSCMAKE 옵션"
  - "Es BSCMAKE 옵션"
  - "파일[C++], BSCMAKE"
  - "Er BSCMAKE 옵션"
  - "BSCMAKE, 파일 제어 옵션"
  - "BSCMAKE 옵션 제어"
  - "El BSCMAKE 옵션"
  - "/El BSCMAKE 옵션"
  - "/Es BSCMAKE 옵션"
  - "Ei BSCMAKE 옵션"
ms.assetid: fa2f1e06-c684-41cf-80dd-6a554835ebd2
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# BSCMAKE 옵션
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 단원에서는 BSCMAKE를 제어하는 데 사용할 수 있는 옵션을 설명합니다.  일부 옵션은 특정 정보를 포함시키거나 제외시켜 찾아보기 정보 파일의 내용을 제어합니다.  제외 옵션을 사용하면 BSCMAKE를 더 빠르게 실행하고 .bsc 파일을 더 작게 만들 수 있습니다.  옵션 이름은 대\/소문자를 구분합니다\(**\/HELP**와 **\/NOLOGO** 제외\)  
  
 Visual Studio 개발 환경 내에서는 **\/NOLOGO** 및 **\/o** 만 사용할 수 있습니다.  프로젝트의 속성 페이지에 액세스하는 방법에 대한 내용은 [Visual C\+\+ 프로젝트 속성 설정](../../ide/working-with-project-properties.md)을 참조하십시오.  
  
 \/Ei \( `filename`...\)  
 지정된 포함 파일의 내용을 찾아보기 정보 파일에서 제외시킵니다.  파일을 여러 개 지정하려면 이름을 공백으로 구분하고 목록을 괄호로 묶습니다.  `filename`을 하나만 지정할 경우에는 괄호가 필요하지 않습니다.  \/**\/Es**를 사용하여 제외되지 않은 파일을 제외시키려면 **\/Es** 옵션과 함께 **\/Ei** 를 사용합니다.  
  
 \/El  
 로컬 기호를 제외시킵니다.  기본값은 로컬 기호를 포함하도록 설정되어 있습니다.  로컬 기호에 대한 자세한 내용은 [.sbr 파일 만들기](../../build/reference/creating-an-dot-sbr-file.md)를 참조하십시오.  
  
 \/Em  
 매크로 본문에서 기호를 제외시킵니다.  찾아보기 정보 파일에 매크로의 이름만 포함하려면 **\/Em** 을 사용합니다.  기본값은 매크로 이름과 매크로 확장 결과를 모두 포함하도록 설정되어 있습니다.  
  
 \/Er \(`symbol`...\)  
 지정된 기호를 찾아보기 정보 파일에서 제외시킵니다.  기호 이름을 여러 개 지정하려면 공백으로 이름을 구분하고 목록을 괄호로 묶습니다.  `symbol`을 하나만 지정할 경우에는 괄호가 필요하지 않습니다.  
  
 \/Es  
 절대 경로로 지정되거나 INCLUDE 환경 변수에 지정된 절대 경로에 있는 모든 포함 파일을 찾아보기 정보 파일에서 제외시킵니다. \(일반적으로 이 파일들은 시스템 포함 파일이며 찾아보기 정보 파일에 필요 없는 많은 정보를 포함하고 있습니다.\) 이 옵션은 경로를 사용하지 않거나 상대 경로를 사용하여 지정된 파일 또는 INCLUDE 환경 변수에 지정된 상대 경로에 있는 파일은 제외시키지 않습니다.  **\/Es**로 제외되지 않은 파일을 제외시키려면 **\/Es** 옵션과 함께 **\/Ei** 를 사용할 수 있습니다.  **\/Es**로 제외되는 파일의 일부만 제외시키려면 **\/Es** 대신 **\/Ei**를 사용하고 제외시킬 파일의 목록을 표시합니다.  
  
 \/errorreport:\[none &#124; prompt &#124; queue &#124; send\]  
 bscmake.exe에서 발생한 내부 오류와 관련된 정보를 Microsoft에 보낼 수 있습니다.  
  
 **\/errorreport**에 대한 자세한 내용은 [\/errorReport\(내부 컴파일러 오류 보고\)](../../build/reference/errorreport-report-internal-compiler-errors.md)을 참조하십시오.  
  
 \/HELP  
 BSCMAKE 명령줄 구문에 대한 요약 정보를 표시합니다.  
  
 \/Iu  
 참조되지 않은 기호를 포함시킵니다.  기본적으로 BSCMAKE는 정의되었지만 참조되지 않은 기호를 기록하지 않습니다.  .sbr 파일이 패킹된 경우에는 참조되지 않은 기호를 컴파일러가 이미 제거했기 때문에 해당 입력 파일에 대해 이 옵션을 사용해도 아무 효과가 없습니다.  
  
 \/n  
 비증분 빌드를 수행합니다.  .bsc 파일의 존재 여부와 상관없이 찾아보기 정보 파일에 대해 전체 빌드를 수행하고 .sbr 파일이 잘리지 않게 하려면 **\/n** 을 사용합니다.  [BSCMAKE에서 .bsc 파일을 빌드하는 방법](../../build/reference/how-bscmake-builds-a-dot-bsc-file.md)을 참조하십시오.  
  
 \/NOLOGO  
 BSCMAKE 저작권 메시지를 표시하지 않습니다.  
  
 \/o `filename`  
 찾아보기 정보 파일의 이름을 지정합니다.  기본적으로 BSCMAKE는 찾아보기 정보 파일에 첫째 .sbr 파일의 기본 이름과 .bsc 확장명을 지정합니다.  
  
 \/S \( `filename`...\)  
 지정된 포함 파일을 처음으로 발견한 경우에만 처리하고 그렇지 않은 경우에는 제외시키도록 BSCMAKE에게 지시합니다.  파일\(.c 또는 .cpp 소스 파일에 대한 헤더 또는 .h 파일\)이 여러 소스 파일에 포함되어 있지만 전처리 지시문에 의해 매번 변경되지 않는 경우 이 옵션을 사용하면 처리 시간을 줄일 수 있습니다.  또한 파일의 변경 내용이 찾아보기 정보 파일에 중요하지 않은 경우에도 이 옵션을 사용할 수 있습니다.  파일을 여러 개 지정하려면 이름을 공백으로 구분하고 목록을 괄호로 묶습니다.  `filename`을 하나만 지정할 경우에는 괄호가 필요하지 않습니다.  해당 파일이 포함될 때마다 제외시키려면 **\/Ei** 또는 **\/Es** 옵션을 사용합니다.  
  
 \/v  
 처리하는 각 .sbr 파일의 이름과 전체 BSCMAKE 실행 정보 등 자세한 정보를 제공합니다.  
  
 \/?  
 BSCMAKE 명령줄 구문에 대한 간단한 요약 정보를 표시합니다.  
  
 다음 명령줄은 BSCMAKE에게 3개의 .sbr 파일에서 MAIN.bsc의 전체 빌드를 수행하도록 지시합니다.  또한 TOOLBOX.h의 중복 인스턴스를 제외시킵니다.  
  
```  
BSCMAKE /n /S toolbox.h /o main.bsc file1.sbr file2.sbr file3.sbr  
```  
  
## 참고 항목  
 [BSCMAKE 참조](../../build/reference/bscmake-reference.md)