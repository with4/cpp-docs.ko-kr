---
title: "-GA (Windows 응용 프로그램 최적화) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLCompilerTool.OptimizeForWindowsApplication
- /ga
dev_langs: C++
helpviewer_keywords:
- /GA compiler option [C++]
- GA compiler option [C++]
- -GA compiler option [C++]
- Optimize for Windows compiler options
ms.assetid: be97323e-15a0-4836-862c-95980b51926a
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 611704120ec99280e0701e06e0e4bd45c95330d4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="ga-optimize-for-windows-application"></a>/GA(Windows 응용 프로그램 최적화)
스레드 로컬 저장소 (TLS) 변수에 액세스 하기 위한.exe 파일에 대 한 보다 효율적인 코드의 결과입니다.  
  
## <a name="syntax"></a>구문  
  
```  
/GA  
```  
  
## <a name="remarks"></a>설명  
 **/GA** 으로 선언 된 데이터에 대 한 액세스 속도 [__declspec (thread)](../../cpp/declspec.md) Windows 기반 프로그램에서입니다. 이 옵션을 설정 하는 경우는 [__tls_index](http://msdn.microsoft.com/library/windows/desktop/ms686749) 매크로 0으로 간주 됩니다.  
  
 사용 하 여 **/GA** DLL 잘못 된 코드가 생성 될 수 있습니다.  
  
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