---
title: 'MIDL 속성 페이지: 고급 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- VC.Project.VCMidlTool.ErrorCheckBounds
- VC.Project.VCMidlTool.ErrorCheckStubData
- VC.Project.VCMidlTool.ErrorCheckAllocations
- VC.Project.VCMidlTool.CPreprocessOptions
- VC.Project.VCMidlTool.UndefinePreprocessorDefinitions
- VC.Project.VCMidlTool.EnableErrorChecks
- VC.Project.VCMidlTool.RedirectOutputAndErrors
- VC.Project.VCMidlTool.ErrorCheckEnumRange
- VC.Project.VCMidlTool.StructMemberAlignment
- VC.Project.VCMidlTool.ErrorCheckRefPointers
- VC.Project.VCMidlTool.ValidateParameters
dev_langs:
- C++
helpviewer_keywords:
- MIDL, property pages
ms.assetid: d1c92e01-f403-4ed6-ab45-4043a3c9c6bb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9b99dae277fec7618c2e7caeb76229edce7a78c2
ms.sourcegitcommit: 7eadb968405bcb92ffa505e3ad8ac73483e59685
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/23/2018
ms.locfileid: "39207762"
---
# <a name="midl-property-pages-advanced"></a>MIDL 속성 페이지: 고급
**MIDL** 폴더의 **고급** 속성 페이지에서 다음 MIDL 컴파일러 옵션을 지정합니다.  
  
-   오류 검사 사용([/error](http://msdn.microsoft.com/library/windows/desktop/aa367324))  
  
-   할당 검사([/error](http://msdn.microsoft.com/library/windows/desktop/aa367324))  
  
-   경계 검사([/error](http://msdn.microsoft.com/library/windows/desktop/aa367324))  
  
-   열거형 범위 검사([/error](http://msdn.microsoft.com/library/windows/desktop/aa367324))  
  
-   참조 포인터 검사([/error](http://msdn.microsoft.com/library/windows/desktop/aa367324))  
  
-   스텁 데이터 검사([/error](http://msdn.microsoft.com/library/windows/desktop/aa367324))  
  
-   매개 변수 유효성 검사([/robust](http://msdn.microsoft.com/library/windows/desktop/aa367363)) \*  
  
-   구조체 멤버 맞춤([/Zp](http://msdn.microsoft.com/library/windows/desktop/aa367388))  
  
-   출력 리디렉션([/o](http://msdn.microsoft.com/library/windows/desktop/aa367351))  
  
-   C 전처리 옵션([/cpp_opt](http://msdn.microsoft.com/library/windows/desktop/aa367318))  
  
-   전처리기 정의 해제([/U](http://msdn.microsoft.com/library/windows/desktop/aa367373))  
  
 \* /robust는 Windows 2000 이상의 컴퓨터용으로 빌드할 때만 사용합니다. ATL 프로젝트를 빌드하고 /robust를 사용하려면 dlldatax.c 파일에서 이 줄을 변경합니다.  
  
```  
#define _WIN32_WINNT 0x0400   //for Windows NT 4.0 or Windows 95 with DCOM  
to   
#define _WIN32_WINNT 0x0500   //for Windows NT 4.0 or Windows 95 with DCOM  
```  
  
 **MIDL** 폴더에서 **고급** 속성 페이지에 액세스하는 방법에 대한 자세한 내용은 [프로젝트 속성 작업](../ide/working-with-project-properties.md)을 참조하세요.  
  
 C++ 프로젝트의 MIDL 옵션에 프로그래밍 방식으로 액세스하는 방법에 대한 자세한 내용은 <xref:Microsoft.VisualStudio.VCProjectEngine.VCMidlTool>을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [MIDL 속성 페이지](../ide/midl-property-pages.md)