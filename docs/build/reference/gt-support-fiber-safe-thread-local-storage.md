---
title: "-GT (파이버 안전 스레드 로컬 저장소 지원) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLCompilerTool.EnableFiberSafeOptimizations
- /gt
dev_langs:
- C++
helpviewer_keywords:
- /GT compiler option [C++]
- GT compiler option [C++]
- thread-local storage
- static thread-local storage and fiber safety
- -GT compiler option [C++]
- fiber-safe static thread-local storage compiler option [C++]
ms.assetid: 071fec79-c701-432b-9970-457344133159
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 86c027a1796f42d7b2932f68aff00136ee0d217f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="gt-support-fiber-safe-thread-local-storage"></a>/GT(파이버 안전 스레드 로컬 저장소 지원)
정적 스레드 로컬 저장소를 사용 하 여 할당 하는 데이터 즉,를 사용 하 여 할당 한 데이터의 파이버 안전을 지원 `__declspec(thread)`합니다.  
  
## <a name="syntax"></a>구문  
  
```  
/GT  
```  
  
## <a name="remarks"></a>설명  
 사용 하 여 데이터 선언 `__declspec(thread)` 스레드 로컬 저장소 (TLS) 배열을 통해 참조 됩니다. TLS 배열이 시스템에서 각 스레드에 대해 관리 주소의 배열입니다. 이 배열에 있는 각 주소는 스레드 로컬 저장소 데이터의 위치를 제공합니다.  
  
 파이버는 스택 및 레지스터 컨텍스트로 구성 되며 다양 한 스레드에서 예약할 수 있는 간단한 개체입니다. 파이버는 스레드에서 실행할 수 있습니다. 파이버는 나중에 다른 스레드를 다시 시작 하므로, TLS 배열의 주소 해야 하지 캐시 하거나 최적화할 공통 부분식으로 함수 호출 중에 (참조는 [/Og (전역 최적화)](../../build/reference/og-global-optimizations.md) 에 대 한 옵션 세부 정보)입니다. **/GT** 같은 최적화를 방지 합니다.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.  
  
2.  **C/C++** 폴더를 클릭합니다.  
  
3.  클릭는 **최적화** 속성 페이지.  
  
4.  수정 된 **파이버 안전 최적화 사용** 속성입니다.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableFiberSafeOptimizations%2A>을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)