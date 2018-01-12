---
title: "-Fe (EXE 파일 이름) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /fe
dev_langs: C++
helpviewer_keywords:
- -Fe compiler option [C++]
- executable files, renaming
- rename file compiler option [C++]
- /Fe compiler option [C++]
- Fe compiler option [C++]
ms.assetid: 49f594fd-5e94-45fe-a1bf-7c9f2abb6437
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 83965ef2bf64f77dbcb1eb9832e7178c30260d16
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="fe-name-exe-file"></a>/Fe(EXE 파일 이름 지정)
이름 및.exe 파일 또는 컴파일러에서 만든 DLL에 대 한 디렉터리를 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
/Fepathname  
```  
  
## <a name="remarks"></a>설명  
 이 옵션이 없으면 컴파일러 사용 하면 파일 확장명이.exe 또는.dll 및 명령줄에 지정 된 첫 번째 소스 또는 개체 파일의 기본 이름을 사용 하 여 기본 이름입니다.  
  
 지정 하는 경우는[(컴파일 없이 링크 사용) /c](../../build/reference/c-compile-without-linking.md), 링크 하지 않고 컴파일할 **/Fe** 영향을 주지 않습니다.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.  
  
2.  클릭는 **링커** 폴더입니다.  
  
3.  클릭는 **일반**속성 페이지.  
  
4.  수정 된 **출력 파일** 속성입니다.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.OutputFile%2A>을 참조하세요.  
  
## <a name="example"></a>예  
 다음 명령줄을 컴파일하고 현재 디렉터리의 모든 C 소스 파일을 연결 합니다. 결과 실행 파일 PROCESS.exe 라는 고 C:\BIN 디렉터리에 생성 됩니다.  
  
```  
CL /FeC:\BIN\PROCESS *.C  
```  
  
## <a name="example"></a>예  
 다음 명령줄의 실행 파일을 만듭니다 `C:\BIN` 첫 번째 소스 나 개체 파일과 동일한 기본 이름을 가진:  
  
```  
CL /FeC:\BIN\ *.C  
```  
  
## <a name="see-also"></a>참고 항목  
 [출력 파일 (/ F) 옵션](../../build/reference/output-file-f-options.md)   
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)   
 [경로 이름 지정](../../build/reference/specifying-the-pathname.md)