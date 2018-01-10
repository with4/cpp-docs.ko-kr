---
title: "MIDL 속성 페이지: 고급 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
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
dev_langs: C++
helpviewer_keywords: MIDL, property pages
ms.assetid: d1c92e01-f403-4ed6-ab45-4043a3c9c6bb
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d6e7dde047c3311c6fd694a91c7a63fcfbcc95d0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="midl-property-pages-advanced"></a>MIDL 속성 페이지: 고급
**고급** 속성 페이지에는 **MIDL** 폴더 MIDL 컴파일러 옵션을 지정 합니다.  
  
-   오류 검사 ([/error](http://msdn.microsoft.com/library/windows/desktop/aa367324))  
  
-   할당 검사 ([/error](http://msdn.microsoft.com/library/windows/desktop/aa367324))  
  
-   범위 확인 ([/error](http://msdn.microsoft.com/library/windows/desktop/aa367324))  
  
-   열거형 범위 검사 ([/error](http://msdn.microsoft.com/library/windows/desktop/aa367324))  
  
-   참조 포인터 검사 ([/error](http://msdn.microsoft.com/library/windows/desktop/aa367324))  
  
-   스텁 데이터 검사 ([/error](http://msdn.microsoft.com/library/windows/desktop/aa367324))  
  
-   매개 변수 유효성 검사 ([/robust](http://msdn.microsoft.com/library/windows/desktop/aa367363)) *  
  
-   구조체 멤버 맞춤 ([/Zp](http://msdn.microsoft.com/library/windows/desktop/aa367388))  
  
-   출력 리디렉션 ([/o](http://msdn.microsoft.com/library/windows/desktop/aa367351))  
  
-   C 전처리 옵션 ([/cpp_opt](http://msdn.microsoft.com/library/windows/desktop/aa367318))  
  
-   전처리기 정의 해제 ([/U](http://msdn.microsoft.com/library/windows/desktop/aa367373))  
  
 \*/ Windows 2000 또는 이상 컴퓨터에 대해 빌드하는 경우에 사용 강력한 됩니다. ATL 프로젝트를 작성 하는 경우를 사용 하려는 /robust, dlldatax.c 파일에서이 줄을 변경 합니다.  
  
```  
#define _WIN32_WINNT 0x0400   //for Windows NT 4.0 or Windows 95 with DCOM  
to   
#define _WIN32_WINNT 0x0500   //for Windows NT 4.0 or Windows 95 with DCOM  
```  
  
 액세스 하는 방법에 대 한 내용은 **고급** 속성 페이지에는 **MIDL** 폴더 참조 [프로젝트 속성 작업](../ide/working-with-project-properties.md)합니다.  
  
 프로그래밍 방식으로 c + + 프로젝트에 대 한 MIDL 옵션에 액세스 하는 방법에 대 한 정보를 참조 하십시오. <xref:Microsoft.VisualStudio.VCProjectEngine.VCMidlTool>합니다.  
  
## <a name="see-also"></a>참고 항목  
 [MIDL 속성 페이지](../ide/midl-property-pages.md)