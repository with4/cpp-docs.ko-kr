---
title: "-WINMDDELAYSIGN (winmd 부분적으로 서명) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VC.Project.VCLinkerTool.WINMDDelaySign
dev_langs: C++
ms.assetid: 445cd602-62cb-400a-8e3a-4beb6572724d
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 79b22e0634a28d208081d29d0fa3ec0cb01456bd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="winmddelaysign-partially-sign-a-winmd"></a>/WINMDDELAYSIGN(winmd에 부분적으로 서명)
파일에 공개 키를 입력하여 Windows 런타임 메타데이터(.winmd) 파일의 일부 서명을 활성화합니다.  
  
```  
/WINMDDELAYSIGN[:NO]  
```  
  
## <a name="remarks"></a>설명  
 유사한는 [/DELAYSIGN](../../build/reference/delaysign-partially-sign-an-assembly.md) .winmd 파일에 적용 되는 링커 옵션입니다. 사용 하 여 **지정 하려면 /WINMDDELAYSIGN** .winmd 파일에 공개 키만 입력 하려는 경우. 기본적으로 링커는 역할 처럼 **/winmddelaysign: no** 에 지정 했습니다; 즉, winmd 파일을 서명 하지 않습니다.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.  
  
2.  선택 된 **링커** 폴더입니다.  
  
3.  선택 된 **Windows 메타 데이터** 속성 페이지.  
  
4.  에 **Windows 메타 데이터 지연 서명** 드롭다운 목록 상자에서 원하는 옵션을 선택 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)