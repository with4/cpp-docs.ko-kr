---
title: BSCMAKE 옵션 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCBscMakeTool.OutputFile
- VC.Project.VCBscMakeTool.SuppressStartupBanner
- VC.Project.VCBscMakeTool.PreserveSBR
dev_langs:
- C++
helpviewer_keywords:
- /v BSCMAKE option
- Iu BSCMAKE option
- browse information files (.bsc), content
- /Er BSCMAKE option
- NOLOGO BSCMAKE option
- /s BSCMAKE option
- /Ei BSCMAKE option
- /o BSCMAKE option
- /NOLOGO BSCMAKE option
- /Iu BSCMAKE option
- s BSCMAKE option (/s)
- /Em BSCMAKE option
- Em BSCMAKE option
- Es BSCMAKE option
- files [C++], BSCMAKE
- Er BSCMAKE option
- BSCMAKE, options for controlling files
- controlling BSCMAKE options
- El BSCMAKE option
- /El BSCMAKE option
- /Es BSCMAKE option
- Ei BSCMAKE option
ms.assetid: fa2f1e06-c684-41cf-80dd-6a554835ebd2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 16fd9bc8813179d23e83ab0a21a84ad815501bf6
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32377857"
---
# <a name="bscmake-options"></a>BSCMAKE 옵션
이 섹션에서는 BSCMAKE를 제어 하는 것에 대 한 사용할 수 있는 옵션을 설명 합니다. 몇 가지 옵션에는 특정 정보를 포함 시키거나 제외 시켜 찾아보기 정보 파일의 내용을 제어 합니다. 제외 옵션 BSCMAKE 더 빠르게 실행을 허용할 수 하 고 더 작은.bsc 파일이 될 수 있습니다. 옵션 이름은 대/소문자 구분 됩니다 (제외 하 고 **/help** 및 **/NOLOGO**).  
  
 만 **/NOLOGO** 및 **/o** Visual Studio 개발 환경 내에서 사용할 수 있습니다.  참조 [Visual c + + 프로젝트 속성 설정](../../ide/working-with-project-properties.md) 에 대 한 내용은 프로젝트의 속성 페이지에 액세스 합니다.  
  
 /Ei ( `filename`...)  
 찾아보기 정보 파일에서 지정된 된 포함 파일의 내용을 제외합니다. 여러 파일을 지정 하려면 이름을 공백으로 구분 하 고 목록을 괄호로 묶습니다. 괄호가 하나만 지정 하는 경우에 필요 하지 않습니다 `filename`합니다. 사용 하 여 **/Ei** 와 함께 **/Es** 으로 제외 되지 않은 파일을 제외 하려면 옵션 **/Es**합니다.  
  
 /El  
 로컬 기호를 제외합니다. 기본값은 로컬 기호를 포함 하도록 합니다. 로컬 기호에 대 한 자세한 내용은 참조 [.sbr 파일 만들기](../../build/reference/creating-an-dot-sbr-file.md)합니다.  
  
 /Em  
 매크로 본문의 기호는 제외 됩니다. 사용 하 여 **/Em** 찾아보기 정보 파일에 매크로 이름만 포함 하도록 합니다. 기본값은 모두 매크로 이름 및 매크로 확장의 결과 포함 하도록 합니다.  
  
 /Er ( `symbol`...)  
 찾아보기 정보 파일에서 지정된 된 기호를 제외합니다. 기호 이름을 여러 개를 지정 하려면 이름을 공백으로 구분 하 고 목록을 괄호로 묶습니다. 괄호가 하나만 지정 하는 경우에 필요 하지 않습니다 `symbol`합니다.  
  
 /Es  
 모든 include 파일은 절대 경로로 지정 되지 않았거나 INCLUDE 환경 변수에 지정 된 절대 경로에서 찾아보기 정보 파일에서 제외 합니다. (시스템 이들은 일반적으로 많은 찾아보기 정보 파일에 필요 하지 않을 수 있는 정보가 포함 된 파일을 포함 합니다.) 이 옵션 없이 경로 또는 상대 경로 또는 INCLUDE에 상대 경로에 파일을 지정 된 파일을 제외 하지 않습니다. 사용할 수는 **/Ei** 옵션과 함께 **/Es** 파일을 제외 하려면 **/Es** 제외 하지 않습니다. 파일 중 일부만 제외 하려면 있는 **/Es** 제외를 사용 하 여 **/Ei** 대신 **/Es** 제외 하려는 파일을 나열 하 고 합니다.  
  
 /errorreport: [없음 &#124; 프롬프트 &#124; 큐 &#124; 송신]  
 Bscmake.exe의 내부 오류에 대 한 정보를 Microsoft로 보낼 수 있습니다.  
  
 대 한 자세한 내용은 **/errorreport**, 참조 [/errorReport (내부 컴파일러 오류 보고)](../../build/reference/errorreport-report-internal-compiler-errors.md)합니다.  
  
 /HELP  
 BSCMAKE 명령줄 구문에 대 한 요약을 표시합니다.  
  
 /Iu  
 참조 되지 않은 기호를 포함합니다. BSCMAKE는 기본적으로 정의 되었지만 참조 되지 않는 모든 기호 기록 하지 않습니다. .Sbr 파일 압축 된, 하는 경우이 옵션은 컴파일러가 이미 참조 되지 않은 기호를 제거 하기 때문에 해당 입력된 파일에 대 한 효과가 없습니다.  
  
 /n  
 비증분 빌드를 강제로 수행합니다. 사용 하 여 **/n** .bsc 파일이 존재 하는지 여부와 상관 없이 찾아보기 정보 파일의 전체 빌드를 수행 하 고.sbr 파일이 잘리지 않도록 합니다. 참조 [BSCMAKE.bsc 파일을 빌드하는 방법](../../build/reference/how-bscmake-builds-a-dot-bsc-file.md)합니다.  
  
 /NOLOGO  
 BSCMAKE 저작권 메시지를 표시 하지 않습니다.  
  
 /o `filename`  
 찾아보기 정보 파일에 대 한 이름을 지정합니다. 기본적으로 BSCMAKE.bsc 확장명 첫 번째.sbr 파일의 기본 이름과 찾아보기 정보 파일을 제공합니다.  
  
 /S ( `filename`...)  
 BSCMAKE 발견 된 처음으로 지정된 된 포함 파일을 처리 하 고 그렇지 않으면 제외 하도록 지시 합니다. 파일 (예: 헤더로, 또는.h, 파일에는.c 또는.cpp 소스 파일) 여러 소스 파일에 포함 되어 있지만 때마다 전처리 지시문에 의해 변경 되지 않는 경우 처리 시간을 절약 하려면이 옵션을 사용 합니다. 파일을 만들려는 찾아보기 정보 파일에 대 한 중요 하지 않은 방법으로 변경 된 경우이 옵션을 사용 하려면 수도 있습니다. 여러 파일을 지정 하려면 이름을 공백으로 구분 하 고 목록을 괄호로 묶습니다. 괄호가 하나만 지정 하는 경우에 필요 하지 않습니다 `filename`합니다. 포함 될 때마다 파일을 제외, 사용 하려는 경우는 **/Ei** 또는 **/Es** 옵션입니다.  
  
 /v  
 처리 중인 각.sbr 파일의 이름 및 전체 BSCMAKE 실행 하는 방법에 대 한 정보를 포함 하는 자세한 정보 출력을 제공 합니다.  
  
 /?  
 BSCMAKE 명령줄 구문에 대 한 간단한 요약을 표시합니다.  
  
 다음 명령줄은 세 개의.sbr 파일에서 MAIN.bsc의 전체 빌드를 수행 해야 하는 BSCMAKE를 알려 줍니다. 또한 TOOLBOX.h의 중복 인스턴스를 제외 하도록 BSCMAKE 하도록 지정 합니다.  
  
```  
BSCMAKE /n /S toolbox.h /o main.bsc file1.sbr file2.sbr file3.sbr  
```  
  
## <a name="see-also"></a>참고 항목  
 [BSCMAKE 참조](../../build/reference/bscmake-reference.md)