---
title: "-cgthreads (코드 생성 스레드) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /cgthreads
dev_langs: C++
helpviewer_keywords:
- /cgthreads compiler option (C++)
- -cgthreads compiler option (C++)
- cgthreads compiler option (C++)
- cgthreads
ms.assetid: 64bc768c-6caa-4baf-9dea-7cfa1ffb01c2
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 846e59b0c1303e70e4ed38b43e4869f1f044f64f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="cgthreads-code-generation-threads"></a>/cgthreads(코드 생성 스레드)
최적화 및 코드 생성에 사용할 cl.exe 스레드 수를 설정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
/cgthreads[1-8]  
```  
  
## <a name="arguments"></a>인수  
 number  
 사용할 cl.exe to의 최대 스레드 수(범위 1~8)  
  
## <a name="remarks"></a>설명  
 **/cgthreads** 옵션 수를 지정 최대 스레드 cl.exe 병렬로 최적화 및 코드에 대 한 컴파일 생성 단계입니다. 사이 공백이 있을 수 있습니다 **/cgthreads** 및 `number` 인수입니다. 기본적으로 cl.exe에서는 4 개의 스레드를 사용 처럼 **/cgthreads4** 지정 되었습니다. 더 많은 프로세서 코어를 사용할 수 있는 경우에는 더 큰 `number` 값으로 인해 빌드 시간이 줄어들 수 있습니다. 이 옵션은 결합 된 경우에 특히 유용 [/GL (전체 프로그램 최적화)](../../build/reference/gl-whole-program-optimization.md)합니다.  
  
 빌드에 여러 수준의 병렬 처리를 지정할 수 있습니다. Msbuild.exe 스위치인 **/maxcpucount** 동시에 실행할 수 있는 MSBuild 프로세스의 수를 지정 합니다. [/MP (여러 프로세스로 빌드)](../../build/reference/mp-build-with-multiple-processes.md) 컴파일러 플래그 cl.exe 컴파일하는 프로세스를 동시에 소스 파일의 수를 지정 합니다. **/cgthreads** 옵션 각 cl.exe 프로세스에서 사용 되는 스레드 수를 지정 합니다. 프로세서는 프로세서 코어와 동일한 수의 스레드를 동시에 실행할 수 있으므로 이러한 모든 옵션에 대해 동시에 더 큰 값을 지정하는 것은 유용하지 않으며 오히려 역효과가 일어날 수 있습니다. 프로젝트를 동시에에서 작성 하는 방법에 대 한 자세한 내용은 참조 [병렬로 여러 프로젝트 빌드](/visualstudio/msbuild/building-multiple-projects-in-parallel-with-msbuild)합니다.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.  
  
2.  선택 된 **구성 속성**, **C/c + +** 폴더입니다.  
  
3.  선택 된 **명령줄** 속성 페이지.  
  
4.  수정 된 **추가 옵션** 포함할 속성을 **/cgthreads**`N`여기서 `N` 은 8, 1에서 값이 고 다음을 선택 **확인**합니다.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)