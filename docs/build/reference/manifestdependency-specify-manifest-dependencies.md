---
title: -MANIFESTDEPENDENCY (매니페스트 종속성 지정) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.AdditionalManifestDependencies
dev_langs:
- C++
helpviewer_keywords:
- MANIFESTDEPENDENCY linker option
- /MANIFESTDEPENDENCY linker option
- -MANIFESTDEPENDENCY linker option
ms.assetid: e4b68313-33a2-4c3e-908e-ac2b9f7d6a73
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8f9b2de39f5b5340eff22c7e22244aca3d05af67
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32376574"
---
# <a name="manifestdependency-specify-manifest-dependencies"></a>/MANIFESTDEPENDENCY(매니페스트 종속성 지정)
```  
/MANIFESTDEPENDENCY:manifest_dependency  
```  
  
## <a name="remarks"></a>설명  
 /MANIFESTDEPENDENCY를 사용 하면에 배치 하는 특성을 지정할 수는 \<종속성 > 매니페스트 파일의 섹션입니다.  
  
 참조 [/MANIFEST (만들기-Side-by-side 어셈블리 매니페스트)](../../build/reference/manifest-create-side-by-side-assembly-manifest.md) 매니페스트 파일을 만드는 방법에 대 한 내용은 합니다.  
  
 대 한 자세한 내용은 \<종속성 > 섹션 매니페스트 파일의 참조 [게시자 구성 파일](http://msdn.microsoft.com/library/aa375682)합니다.  
  
 /MANIFESTDEPENDENCY 정보 링커 두 가지 방법 중 하나에 전달 될 수 있습니다.  
  
-   명령줄에서 직접 (또는 지시 파일에서) /MANIFESTDEPENDENCY를 사용 합니다.  
  
-   통해는 [주석](../../preprocessor/comment-c-cpp.md) pragma입니다.  
  
 다음 예제에서는 pragma를 통해 전달 /MANIFESTDEPENDENCY 주석  
  
```  
#pragma comment(linker, "\"/manifestdependency:type='Win32' name='Test.Research.SampleAssembly' version='6.0.0.0' processorArchitecture='X86' publicKeyToken='0000000000000000' language='*'\"")  
```  
  
 매니페스트 파일에 다음 항목에 발생합니다.  
  
```  
<dependency>  
  <dependentAssembly>  
    <assemblyIdentity type='Win32' name='Test.Research.SampleAssembly' version='6.0.0.0' processorArchitecture='X86' publicKeyToken='0000000000000000' language='*' />  
  </dependentAssembly>  
</dependency>  
```  
  
 같은 /MANIFESTDEPENDENCY 주석은 다음과 같이 명령줄에서 전달 될 수 있습니다.  
  
```  
"/manifestdependency:type='Win32' name='Test.Research.SampleAssembly' version='6.0.0.0' processorArchitecture='X86' publicKeyToken='0000000000000000' language='*'\"  
```  
  
 링커에서 /MANIFESTDEPENDENCY 의견을 수집 하 고 중복 항목이 제거 후 매니페스트 파일에 결과 XML 문자열을 추가 합니다.  링커가 충돌 하는 항목을 찾은, 매니페스트 파일이 손상 되 고 응용 프로그램이 시작 되지 것입니다 (항목에서 오류 원인을 나타내는 이벤트 로그에 추가 될 수 있습니다).  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.  
  
2.  확장 된 **구성 속성** 노드.  
  
3.  확장 된 **링커** 노드.  
  
4.  선택 된 **매니페스트 파일** 속성 페이지.  
  
5.  수정 된 **추가 매니페스트 종속성** 속성입니다.  
  
### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
1.  <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalManifestDependencies%2A>을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)