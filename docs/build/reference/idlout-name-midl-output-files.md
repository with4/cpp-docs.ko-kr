---
title: "-IDLOUT (MIDL 출력 파일 이름) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /idlout
- VC.Project.VCLinkerTool.MergedIDLBaseFileName
dev_langs: C++
helpviewer_keywords:
- MIDL, output file names
- .idl files, path
- MIDL
- /IDLOUT linker option
- IDL files, path
- -IDLOUT linker option
- IDLOUT linker option
ms.assetid: 10d00a6a-85b4-4de1-8732-e422c6931509
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8f9f798c31fc4b492565c3406f0cb26251a208d4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="idlout-name-midl-output-files"></a>/IDLOUT(MIDL 출력 파일 이름 지정)
```  
/IDLOUT:[path\]filename  
```  
  
## <a name="parameters"></a>매개 변수  
 *path*  
 절대 또는 상대 경로 사양입니다. 경로 지정 하 여 영향을 미칠 있습니다 프로그램.idl 파일의 위치만 다른 모든 파일은 프로젝트 디렉터리에 배치 됩니다.  
  
 *filename*  
 MIDL 컴파일러에 의해 생성 된.idl 파일의 이름을 지정 합니다. 파일 확장명이 없는 것으로 간주 됩니다. 지정 *filename*.idl.idl 확장 하려는 경우.  
  
## <a name="remarks"></a>설명  
 /IDLOUT 옵션 이름 및.idl 파일의 확장명을 지정합니다.  
  
 가 프로젝트에 연결 하는 경우 Visual c + + 링커 MIDL 컴파일러 호출 되는 [모듈](../../windows/module-cpp.md) 특성입니다.  
  
 /IDLOUT에 MIDL 컴파일러와 관련 된 다른 출력 파일의 파일 이름을 지정 합니다.  
  
-   *filename*.tlb  
  
-   *filename*_p.c  
  
-   *filename*_i.c  
  
-   *filename*.h  
  
 *filename* /IDLOUT으로 전달 하는 매개 변수입니다. 경우 [/TLBOUT](../../build/reference/tlbout-name-dot-tlb-file.md) .tlb 파일 /TLBOUT에서 해당 이름을 가져오는 지정 된 *filename*합니다.  
  
 /IDLOUT 아니고 /TLBOUT 지정 하면 링커가 vc70.tlb, vc70.idl, vc70_p.c, vc70_i.c, 및 vc70.h 만들어집니다.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [Visual c + + 프로젝트 속성 설정](../../ide/working-with-project-properties.md)합니다.  
  
2.  클릭는 **링커** 폴더입니다.  
  
3.  클릭는 **포함 IDL** 속성 페이지.  
  
4.  수정 된 **병합 IDL 기본 파일 이름** 속성입니다.  
  
### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.MergedIDLBaseFileName%2A>을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)   
 [/IGNOREIDL (특성 처리을 MIDL로)](../../build/reference/ignoreidl-don-t-process-attributes-into-midl.md)   
 [/MIDL (MIDL 명령줄 옵션을 지정 합니다.)](../../build/reference/midl-specify-midl-command-line-options.md)   
 [특성을 사용하는 프로그램 빌드](../../windows/building-an-attributed-program.md)