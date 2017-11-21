---
title: "-Yu (미리 컴파일된 헤더 파일 사용) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /yu
dev_langs: C++
helpviewer_keywords:
- Yu compiler option [C++]
- /Yu compiler option [C++]
- -Yu compiler option [C++]
- PCH files, use existing
- .pch files, use existing
- precompiled header files, use existing
ms.assetid: 24f1bd0e-b624-4296-a17e-d4b53e374e1f
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: c0eb123cca28fdae379b387aaf09d0a200a88287
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="yu-use-precompiled-header-file"></a>/Yu(미리 컴파일된 헤더 파일 사용)
현재 컴파일에서 기존의 미리 컴파일된 헤더 (.pch) 파일을 사용 하려면 컴파일러를 지시 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
/Yu[filename]  
```  
  
## <a name="arguments"></a>인수  
 *filename*  
 사용 하 여 소스 파일에 포함 된 헤더 파일의 이름은 **#include** 전처리기 지시문입니다.  
  
## <a name="remarks"></a>설명  
 포함 파일의 이름을 둘 다에 대해 동일 해야는 **/Yc** 프로그램과 미리 컴파일된 헤더를 만드는 옵션 후속 **/Yu** 미리 컴파일된 헤더 사용을 지정 하는 옵션입니다.  
  
 에 대 한 **/Yc**, `filename` 위치를 지정는 미리 컴파일 중지; 컴파일러가 모든 코드 컴파일하며 `filename` 포함 파일 및 확장의 기본 이름을 사용 하 여 미리 컴파일된 헤더의 결과 .pch 합니다.  
  
 .Pch 파일을 만들어야 사용 하 여 **/Yc**합니다.  
  
 컴파일러는 미리 컴파일된으로.h 파일 하기 전에 이러한 모든 코드를 처리 합니다. 뒤에 건너뜁니다 고 **#include** .h 파일에 연결 된 지시문을.pch 파일에 포함 된 코드를 사용 하 고 다음 모든 코드를 컴파일합니다 `filename`합니다.  
  
 명령줄에서 없습니다 사이 공백을 **/Yu** 및 `filename`합니다.  
  
 지정 하는 경우는 **/Yu** 옵션 없이 소스 프로그램 파일 이름 포함 해야 합니다는 [#pragma hdrstop](../../preprocessor/hdrstop.md) .pch 파일, 미리 컴파일된 헤더 파일 이름을 지정 하는 pragma입니다. 이 경우 컴파일러에서 미리 컴파일된 헤더 (.pch 파일)로 명명을 사용 [/Fp (이름입니다. Pch 파일)](../../build/reference/fp-name-dot-pch-file.md)합니다. 컴파일러는 해당 pragma의 위치를 건너뛰고 pragma를 사용 하면 지정 된 미리 컴파일된 헤더 파일에서 컴파일된 상태를 복원만 pragma 뒤에 오는 코드를 컴파일합니다. 경우 **#pragma hdrstop** 파일 이름 확장명이.pch 인 소스 파일의 기본 이름에서 파생 된 이름으로 파일에 대 한 컴파일러 검색을 지정 하지 않습니다. 사용할 수도 있습니다는 **/Fp** 다른.pch 파일을 지정 하는 옵션입니다.  
  
 지정 하는 경우는 **/Yu** 및 파일 이름 없이 옵션을 지정 하지 않으면는 **hdrstop** pragma를 사용 하면 오류 메시지가 생성 되는 컴파일 되 고 실패 합니다.  
  
 경우는 **/Yc** `filename` 및 **/Yu** `filename` 옵션 같은 명령줄에서 발생 하 고 동일한 파일 이름을 참조 **/Yc** `filename` 사용 우선 순위가 최대 모든 코드 미리 컴파일 및 명명 된 파일을 포함 합니다. 이 기능은 메이크파일 작성을 단순화 합니다.  
  
 .Pch 파일 시스템 환경에 대 한 정보와 프로그램에 대 한 메모리 주소 정보를 포함 하므로 만들어진 컴퓨터에서 pch에 대 한 파일에만 사용 해야 합니다.  
  
 미리 컴파일된 헤더에 대 한 자세한 내용은 다음을 참조 하세요.  
  
-   [/Y (미리 컴파일된 헤더)](../../build/reference/y-precompiled-headers.md)  
  
-   [미리 컴파일된 헤더 파일 만들기](../../build/reference/creating-precompiled-header-files.md)  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  지정 [/Yc (미리 컴파일된 헤더 파일 만들기)](../../build/reference/yc-create-precompiled-header-file.md) 프로젝트에서.cpp 파일입니다.  
  
2.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.  
  
3.  **C/C++** 폴더를 클릭합니다.  
  
4.  클릭는 **미리 컴파일된 헤더** 속성 페이지.  
  
5.  수정 된 **파일에서 PCH 만들기/사용** 속성 또는 **미리 컴파일된 헤더 만들기/사용** 속성입니다.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.PrecompiledHeaderThrough%2A> 및 <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.UsePrecompiledHeader%2A>을 참조하십시오.  
  
## <a name="examples"></a>예제  
 하는 경우 다음 코드:  
  
```  
#include <afxwin.h>   // Include header for class library  
#include "resource.h" // Include resource definitions  
#include "myapp.h"    // Include information specific to this app  
...  
```  
  
 명령줄을 사용 하 여 컴파일되며 `CL /YuMYAPP.H PROG.CPP`, 컴파일러는 3 개를 처리 하지 않습니다 전처리 파일 (및 모든 파일)의 세 가지 모두에 포함 된 문은 하지만 MYAPP.pch에서 사용 하 여 미리 컴파일된 코드를 함으로써 포함 합니다.  
  
 사용할 수는 [/Fp (이름입니다. Pch 파일)](../../build/reference/fp-name-dot-pch-file.md) 옵션과 함께 **/Yu** 이름에는 파일 이름 인수가 간에 차이가 있는 경우.pch 파일의 이름을 지정 하는 옵션 **/Yc** 다음과 같이 소스 파일의 기본 이름 또는 다음:  
  
```  
CL /YuMYAPP.H /FpMYPCH.pch PROG.CPP  
```  
  
 이 명령은 MYPCH.pch 라는 미리 컴파일된 헤더 파일을 지정 합니다. 컴파일러의 내용을 사용 하 여 모든까지 헤더 파일 포함 MYAPP.h의 컴파일된 상태를 복원 하 합니다. 컴파일러는 MYAPP.h 다음에 발생 하는 코드를 다음 컴파일하 **포함** 문.  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)