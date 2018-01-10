---
title: "-F (스택 크기 설정) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /f
dev_langs: C++
helpviewer_keywords:
- set stack size compiler option
- F compiler option [C++]
- -F compiler option [C++]
- /F compiler option [C++]
- stack, setting size
ms.assetid: 17320b6f-8305-445b-9ec2-75833f4b29e0
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5b464a4fb28eb83ef0570416d0cb18fd8f965e0a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="f-set-stack-size"></a>/F(스택 크기 설정)
프로그램의 스택 크기를 바이트 단위로 설정 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
/F number  
```  
  
## <a name="arguments"></a>인수  
 `number`  
 스택 크기 (바이트)입니다.  
  
## <a name="remarks"></a>설명  
 이 옵션이 없으면 스택 크기는 1MB로 기본값입니다. `number` 10 진수 또는 C 언어 표기법에서 인수 수 있습니다. 인수는 링커에 의해 허용 하는 최대 스택 크기를 1에서 까지입니다. 링커는 가장 가까운 4 바이트에 지정된 된 값으로 반올림합니다. 사이 공백을 **/F** 및 `number` 선택 사항입니다.  
  
 프로그램 스택 오버플로 메시지를 가져오면 스택 크기를 늘려야 할 수 있습니다.  
  
 또한 스택 크기를 설정할 수 있습니다.  
  
-   사용 하 여 **/stack** 링커 옵션입니다. 자세한 내용은 참조 [/stack](../../build/reference/stack.md)합니다.  
  
-   EDITBIN를 사용 하 여.exe 파일입니다. 자세한 내용은 참조 [EDITBIN 참조](../../build/reference/editbin-reference.md)합니다.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.  
  
2.  **C/C++** 폴더를 클릭합니다.  
  
3.  **명령줄** 속성 페이지를 클릭합니다.  
  
4.  **추가 옵션** 상자에 컴파일러 옵션을 입력합니다.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)