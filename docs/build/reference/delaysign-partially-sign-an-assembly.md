---
title: "-DELAYSIGN (부분적으로 어셈블리 서명) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /delaysign
- VC.Project.VCLinkerTool.DelaySign
dev_langs:
- C++
helpviewer_keywords:
- /DELAYSIGN linker option
- DELAYSIGN linker option
- -DELAYSIGN linker option
ms.assetid: 15244d30-3ecb-492f-a408-ffe81f38de20
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f67e4da2d85d94854ec0802450b41333d6577175
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="delaysign-partially-sign-an-assembly"></a>/DELAYSIGN(어셈블리에 부분적으로 서명)
```  
/DELAYSIGN[:NO]  
```  
  
## <a name="remarks"></a>설명  
 다음은 각 문자에 대한 설명입니다.  
  
 아니요  
 어셈블리가 부분적으로 서명 되지를 지정 합니다.  
  
## <a name="remarks"></a>설명  
 사용 하 여 **/DELAYSIGN** 어셈블리의 공개 키를 저장 하려는 경우. 기본값은 **/delaysign: no**합니다.  
  
 **/DELAYSIGN** 옵션은 효과가 없습니다 함께 사용 해야 [/KEYFILE](../../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md) 또는 [/KEYCONTAINER](../../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md)합니다.  
  
 완전히 서명된 어셈블리를 요청할 경우 컴파일러는 매니페스트(어셈블리 메타데이터)가 포함된 파일을 해시하고 개인 키로 해당 해시에 서명합니다. 결과로 생성되는 디지털 서명은 매니페스트가 포함된 파일에 저장됩니다. 어셈블리 서명이 연기 되 면 링커 계산 및 나중에 서명을 추가할 수 있도록 파일에 서명을 하지만 공간을 예약을 저장 하지 않습니다.  
  
 예를 들어,를 사용 하 여 **/DELAYSIGN** 하면 테스터가 어셈블리를 전역 캐시에 넣을 수 있습니다. 테스트를 마친 후에 어셈블리에 개인 키를 배치 하 여 어셈블리에 완전히 서명할 수 있습니다.  
  
 참조 [강력한 이름 어셈블리 (어셈블리 서명) (C + + /cli CLI)](../../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md) 및 [어셈블리 서명 연기](/dotnet/framework/app-domains/delay-sign-assembly) 어셈블리 서명에 대 한 자세한 내용은 합니다.  
  
 어셈블리 생성에 영향을 주는 다른 링커 옵션은:  
  
-   [/ASSEMBLYDEBUG](../../build/reference/assemblydebug-add-debuggableattribute.md)  
  
-   [/ASSEMBLYLINKRESOURCE](../../build/reference/assemblylinkresource-link-to-dotnet-framework-resource.md)  
  
-   [/ASSEMBLYMODULE](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md)  
  
-   [/ASSEMBLYRESOURCE](../../build/reference/assemblyresource-embed-a-managed-resource.md)  
  
-   [/NOASSEMBLY](../../build/reference/noassembly-create-a-msil-module.md)  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [Visual c + + 프로젝트 속성 설정](../../ide/working-with-project-properties.md)합니다.  
  
2.  클릭는 **링커** 폴더입니다.  
  
3.  **명령줄** 속성 페이지를 클릭합니다.  
  
4.  에 옵션을 입력에서 **추가 옵션** 상자입니다.  
  
### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)