---
title: "-GH (_pexit 후크 함수 사용) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: _pexit
dev_langs: C++
helpviewer_keywords:
- /Gh compiler option [C++]
- Gh compiler option [C++]
- _pexit function
- -Gh compiler option [C++]
ms.assetid: 93181453-2676-42e5-bf63-3b19e07299b6
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 02cfdd783a698a3397e84fa62b7252399570dc84
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="gh-enable-pexit-hook-function"></a>/GH(_pexit 후크 함수 사용)
호출 된 `_pexit` 함수의 모든 메서드 또는 함수의 끝에 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
/GH  
```  
  
## <a name="remarks"></a>설명  
 `_pexit` 함수 라이브러리의 일부가 아니며에 대 한 정의에 `_pexit`합니다.  
  
 명시적으로 호출 하려는 경우가 아니면 `_pexit`, 프로토타입을 제공 필요가 없습니다. 함수 처럼 다음과 같은 프로토타입을 이전의 하 고 항목에 모든 레지스터의 내용을 강제 종료 시 변경 되지 않은 콘텐츠를 팝에 나타나야 합니다.  
  
```  
void __declspec(naked) _cdecl _pexit( void );  
```  
  
 `_pexit`유사한 `_penter`; 참조 [/Gh (_penter 후크 함수 사용)](../../build/reference/gh-enable-penter-hook-function.md) 작성 하는 방법의 예는 `_pexit` 함수입니다.  
  
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