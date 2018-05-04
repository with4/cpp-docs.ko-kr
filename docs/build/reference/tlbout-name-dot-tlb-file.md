---
title: -TLBOUT (이름입니다. TLB 파일) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.TypeLibraryFile
- /tlbout
dev_langs:
- C++
helpviewer_keywords:
- tlb files, renaming
- TLBOUT linker option
- /TLBOUT linker option
- .tlb files, renaming
- -TLBOUT linker option
ms.assetid: 0df6d078-2e48-46c9-a1a5-02674d85dce8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1cc4103c387fe7a3dae68b642c10e326b361c54a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="tlbout-name-tlb-file"></a>/TLBOUT(.TLB 파일 이름 지정)
```  
/TLBOUT:[path\]filename  
```  
  
## <a name="remarks"></a>설명  
 다음은 각 문자에 대한 설명입니다.  
  
 *path*  
 절대 또는 상대 경로 지정은.tlb 파일을 만들 위치입니다.  
  
 *filename*  
 MIDL 컴파일러에 의해 만들어진.tlb 파일의 이름을 지정 합니다. 파일 확장명이 없는 것으로 간주 됩니다. 지정 *filename*.tlb.tlb 확장명을 선택 합니다.  
  
## <a name="remarks"></a>설명  
 /TLBOUT 옵션 이름 및.tlb 파일의 확장명을 지정합니다.  
  
 가 프로젝트에 연결 하는 경우 Visual c + + 링커 MIDL 컴파일러 호출 되는 [모듈](../../windows/module-cpp.md) 특성입니다.  
  
 .Tlb 파일에서 이름을 받습니다 /TLBOUT 지정 하지 않으면 [/IDLOUT](../../build/reference/idlout-name-midl-output-files.md) *filename*합니다. /IDLOUT을 지정 하지 않으면.tlb 파일 vc70.tlb을 호출 됩니다.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [Visual c + + 프로젝트 속성 설정](../../ide/working-with-project-properties.md)합니다.  
  
2.  클릭는 **링커** 폴더입니다.  
  
3.  클릭는 **포함 IDL** 속성 페이지.  
  
4.  수정 된 **형식 라이브러리** 속성입니다.  
  
### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
1.  <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.TypeLibraryFile%2A>을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)   
 [/IGNOREIDL (특성 처리을 MIDL로)](../../build/reference/ignoreidl-don-t-process-attributes-into-midl.md)   
 [/MIDL (MIDL 명령줄 옵션을 지정 합니다.)](../../build/reference/midl-specify-midl-command-line-options.md)   
 [특성을 사용하는 프로그램 빌드](../../windows/building-an-attributed-program.md)