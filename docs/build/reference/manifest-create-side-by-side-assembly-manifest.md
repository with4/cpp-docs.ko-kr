---
title: "-매니페스트 (Side-by-side-어셈블리 매니페스트 만들기) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.GenerateManifest
dev_langs:
- C++
helpviewer_keywords:
- -MANIFEST linker option
- /MANIFEST linker option
- MANIFEST linker option
ms.assetid: 98c52e1e-712c-4f49-b149-4d0a3501b600
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: bb26957109a558b48d6252e042e9082f7357fbd7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="manifest-create-side-by-side-assembly-manifest"></a>/MANIFEST(side-by-side 어셈블리 매니페스트 만들기)
```  
/MANIFEST[:{EMBED[,ID=#]|NO}]  
```  
  
## <a name="remarks"></a>설명  
 / 매니페스트 링커가-side-by-side 매니페스트 파일을 만들도록 지정 합니다. 매니페스트 파일에 대 한 자세한 내용은 참조 [매니페스트 파일 참조](http://msdn.microsoft.com/library/aa375632)합니다.  
  
 기본값은 /MANIFEST 합니다.  
  
 /MANIFEST:EMBED 옵션은 링커가 이미지의 매니페스트 파일을 RT_MANIFEST 유형의 리소스로 포함하도록 지정합니다. 선택적인 `ID` 매개 변수는 매니페스트에 사용할 리소스 ID입니다. 실행 파일의 경우 값 1을 사용합니다. DLL의 경우에는 개인 종속성을 지정하기 위해 값 2를 사용합니다. `ID` 매개 변수가 지정되지 않은 경우에는 /DLL 옵션이 설정된 경우 기본값이 2이고, 그렇지 않으면 기본값이 1입니다.  
  
 Visual Studio 2008부터, 실행 파일을 매니페스트 파일 사용자 계정 컨트롤 (UAC) 정보를 지정 하는 섹션을 포함 합니다. /MANIFEST을 지정 하지만 둘 다를 지정 하는 경우 [/MANIFESTUAC](../../build/reference/manifestuac-embeds-uac-information-in-manifest.md) 나 [/DLL](../../build/reference/dll-build-a-dll.md)로 UAC 수준 설정 된 기본 UAC 조각이 *asInvoker* 를 매니페스트에 삽입 됩니다. UAC 수준에 대 한 자세한 내용은 참조 [/MANIFESTUAC (매니페스트에 UAC 포함 정보)](../../build/reference/manifestuac-embeds-uac-information-in-manifest.md)합니다.  
  
 UAC에 대해 기본 동작을 변경하려면 다음 중 하나를 수행합니다.  
  
-   /MANIFESTUAC 옵션을 지정하고 UAC 수준을 원하는 수준으로 설정합니다.  
  
-   또는 매니페스트에서 UAC 조각을 생성하지 않으려는 경우 /MANIFESTUAC:NO 옵션을 지정합니다.  
  
 /MANIFEST을 지정 하지 않으면 하면서 지정 않아야 하는 경우 [/MANIFESTDEPENDENCY](../../build/reference/manifestdependency-specify-manifest-dependencies.md) 주석의 매니페스트 파일이 생성 됩니다. /MANIFEST:NO를 지정하면 매니페스트 파일이 생성되지 않습니다.  
  
 /MANIFEST를 지정할 경우, 매니페스트 파일의 이름이 출력 파일의 이름과 동일하지만 파일 이름에 .manifest가 추가됩니다. 예를 들어 출력 파일 이름이 MyFile.exe이면, 매니페스트 파일 이름은 MyFile.exe.manifest입니다.  /MANIFESTFILE를 지정 하는 경우:*이름*, 매니페스트 이름은에 지정한 수 만큼 *이름*합니다.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.  
  
2.  확장 된 **구성 속성** 노드.  
  
3.  확장 된 **링커** 노드.  
  
4.  선택 된 **매니페스트 파일** 속성 페이지.  
  
5.  수정 된 **매니페스트 생성** 속성입니다.  
  
### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
1.  <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.GenerateManifest%2A>을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)