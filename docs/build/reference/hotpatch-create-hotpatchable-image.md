---
title: -hotpatch (핫 패치 가능 이미지 만들기) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /hotpatch
- VC.Project.VCCLCompilerTool.CreateHotpatchableImage
dev_langs:
- C++
helpviewer_keywords:
- hot patching
- -hotpatch compiler option [C++]
- /hotpatch compiler option [C++]
- hotpatching
ms.assetid: aad539b6-c053-4c78-8682-853d98327798
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cb0f27c8da03104ee3633d9ea1a5f1232407931e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32376207"
---
# <a name="hotpatch-create-hotpatchable-image"></a>/hotpatch(핫 패치 가능 이미지 만들기)
핫 패치 가능한 이미지를 준비합니다.  
  
## <a name="syntax"></a>구문  
  
```  
/hotpatch  
```  
  
## <a name="remarks"></a>설명  
 때 **/hotpatch** 사용 되는 컴파일, 컴파일러 하면 확인 각 함수의 첫 번째 명령이 최소한 2 바이트는 핫 패치 기능에 필요한 합니다.  
  
 사용 하 여 프로그램 이미지 핫 패치 가능 하기 위한 준비를 완료 하려면 **/hotpatch** 사용 해야 컴파일할 [/FUNCTIONPADMIN (핫 패치 가능 이미지 만들기)](../../build/reference/functionpadmin-create-hotpatchable-image.md) 에 연결 합니다. 컴파일하고 cl.exe를 한 호출을 사용 하 여 이미지를 연결 하면 **/hotpatch** 의미 **/functionpadmin**합니다.  
  
 지침 항상 2 바이트 되므로 또는 ARM 아키텍처에서 더 큰 않기 때문에 컴파일 항상 처리 x64 처럼 **/hotpatch** 지정 지정할 필요가 없습니다 **/hotpatch** 때 이러한 대상;에 대해 컴파일 하지만 사용 하 여 여전히 연결 해야 **/functionpadmin** 핫 패치 가능한 이미지를 만들려고 합니다. **/hotpatch** 컴파일러 옵션만 영향을 줌 x86 컴파일입니다.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.  
  
2.  선택 된 **C/c + +** 폴더입니다.  
  
3.  선택 된 **명령줄** 속성 페이지.  
  
4.  컴파일러 옵션을 추가 하는 **추가 옵션** 상자입니다.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>을 참조하세요.  
  
## <a name="guidance"></a>지침  
 업데이트 관리에 대 한 자세한 내용은 "업데이트 관리에 대 한 보안 지침"에서 참조 [ http://www.microsoft.com/technet/security/guidance/PatchManagement.mspx ](http://www.microsoft.com/technet/security/guidance/PatchManagement.mspx)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)