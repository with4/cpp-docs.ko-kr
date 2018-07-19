---
title: -TLBID (TypeLib 리소스 ID 지정) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /tlbid
- VC.Project.VCLinkerTool.TypeLibraryResourceID
dev_langs:
- C++
helpviewer_keywords:
- tlb files, specifying resource ID
- -TLBID linker option
- .tlb files, specifying resource ID
- /TLBID linker option
- TLBID linker option
- type libraries, specifying resource ID
ms.assetid: 434b28a2-4656-4d52-ac82-8b18bf486fb2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: acea8de3f656da54a0697dc5b980dd4913054a00
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32375167"
---
# <a name="tlbid-specify-resource-id-for-typelib"></a>/TLBID(TypeLib의 리소스 ID 지정)
```  
/TLBID:id  
```  
  
## <a name="remarks"></a>설명  
 다음은 각 문자에 대한 설명입니다.  
  
 `id`  
 링커 생성 형식 라이브러리에 대 한 사용자 지정 값입니다. 기본 리소스 id 1 대신 사용 됩니다.  
  
## <a name="remarks"></a>설명  
 특성을 사용 하는 프로그램을 컴파일할 때 링커가에서는 형식 라이브러리를 만듭니다. 리소스 ID 1 형식 라이브러리에 할당 합니다.  
  
 이 리소스 ID 나와 기존 리소스 충돌을 /TLBID와 다른 ID를 지정할 수 있습니다. 에 전달할 수 있는 값의 범위 `id` 는 1에서 65535 까지입니다.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [Visual c + + 프로젝트 속성 설정](../../ide/working-with-project-properties.md)합니다.  
  
2.  클릭는 **링커** 폴더입니다.  
  
3.  클릭는 **포함 IDL** 속성 페이지.  
  
4.  수정 된 **TypeLib 리소스 ID** 속성입니다.  
  
### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
1.  <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.TypeLibraryResourceID%2A>을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)