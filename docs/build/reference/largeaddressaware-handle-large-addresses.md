---
title: "-LARGEADDRESSAWARE (큰 주소 처리) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.LargeAddressAware
- /largeaddressaware
dev_langs:
- C++
helpviewer_keywords:
- LARGEADDRESSAWARE linker option
- -LARGEADDRESSAWARE linker option
- /LARGEADDRESSAWARE linker option
ms.assetid: a29756c8-e893-47a9-9750-1f0d25359385
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9ecda14f6faf7230066bb1c2b374ca475cc98cb1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="largeaddressaware-handle-large-addresses"></a>/LARGEADDRESSAWARE(큰 주소 처리)
```  
/LARGEADDRESSAWARE[:NO]  
```  
  
## <a name="remarks"></a>설명  
 /LARGEADDRESSAWARE 옵션을 사용 하면 링커에서 응용 프로그램이 2gb를 넘는 주소를 처리할 수 있습니다. 64 비트 컴파일러에서는이 옵션이 기본적으로 사용 됩니다. 32 비트 컴파일러에서 /largeaddressaware: no /LARGEADDRESSAWARE 링커 줄에 그렇지 않으면 지정 되지 않은 경우 사용 됩니다.  
  
 응용 프로그램에 /LARGEADDRESSAWARE, DUMPBIN 링크 된 경우 [/HEADERS](../../build/reference/headers.md) 그 결과 정보가 표시 됩니다.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [Visual c + + 프로젝트 속성 설정](../../ide/working-with-project-properties.md)합니다.  
  
2.  클릭는 **링커** 폴더입니다.  
  
3.  클릭는 **시스템** 속성 페이지.  
  
4.  수정 된 **큰 주소 사용** 속성입니다.  
  
### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.LargeAddressAware%2A>을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)