---
title: "-IGNOREIDL (Don &#39; t 프로세스 특성을 MIDL로) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.IgnoreEmbeddedIDL
- /ignoreidl
dev_langs: C++
helpviewer_keywords:
- IGNOREIDL linker option
- -IGNOREIDL linker option
- /IGNOREIDL linker option
ms.assetid: 29514098-6a1c-4317-af2f-1dc268972780
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: fe2f1d33f9269380bf0d914d5805cce3b0a92b90
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="ignoreidl-don39t-process-attributes-into-midl"></a>/IGNOREIDL (Don &#39; t 프로세스 특성을 MIDL로)
```  
/IGNOREIDL  
```  
  
## <a name="remarks"></a>설명  
 /IGNOREIDL 옵션은 지정는 모든 [IDL 특성](../../windows/idl-attributes.md) 소스.idl 파일에 코드 처리 되지 않도록 합니다.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [Visual c + + 프로젝트 속성 설정](../../ide/working-with-project-properties.md)합니다.  
  
2.  클릭는 **링커** 폴더입니다.  
  
3.  클릭는 **포함 IDL** 속성 페이지.  
  
4.  수정 된 **포함 IDL 무시** 속성입니다.  
  
### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.IgnoreEmbeddedIDL%2A>을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)   
 [/IDLOUT (MIDL 출력 파일 이름)](../../build/reference/idlout-name-midl-output-files.md)   
 [/TLBOUT (이름입니다. TLB 파일)](../../build/reference/tlbout-name-dot-tlb-file.md)   
 [/MIDL (MIDL 명령줄 옵션을 지정 합니다.)](../../build/reference/midl-specify-midl-command-line-options.md)   
 [특성을 사용하는 프로그램 빌드](../../windows/building-an-attributed-program.md)