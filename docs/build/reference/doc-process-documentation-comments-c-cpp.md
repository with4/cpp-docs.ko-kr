---
title: -doc (문서 주석 처리) (C/c + +) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.GenerateXMLDocumentationFiles
- /doc
- VC.Project.VCCLCompilerTool.XMLDocumentationFileName
dev_langs:
- C++
helpviewer_keywords:
- /doc compiler option [C++]
- comments, C++ code
- XML documentation, comments in source files
- -doc compiler option [C++]
ms.assetid: b54f7e2c-f28f-4f46-9ed6-0db09be2cc63
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 899ff6b774c365ce9df3019ef5ba6d08d0d7b93d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="doc-process-documentation-comments-cc"></a>/doc(문서 주석 처리)(C/C++)
컴파일러가 문서 주석을 소스 코드 파일에서 및 문서 주석이 있는 있는 각 소스 코드 파일에 대 한.xdc 파일을 만들려면 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
/doc[name]  
```  
  
## <a name="arguments"></a>인수  
 `name`  
 컴파일러를 만들.xdc 파일의 이름입니다. 하나의.cpp 파일이 컴파일에 전달 될 때만 유효 합니다.  
  
## <a name="remarks"></a>설명  
 .Xdc 파일 xdcmake.exe와.xml 파일로 처리 됩니다. 자세한 내용은 참조 [XDCMake 참조](../../ide/xdcmake-reference.md)합니다.  
  
 소스 코드 파일에 문서 주석을 추가할 수 있습니다. 자세한 내용은 참조 [문서 주석에 대 한 권장 태그](../../ide/recommended-tags-for-documentation-comments-visual-cpp.md)합니다.  
  
 생성된 된.xml 파일에서 IntelliSense를 사용 하려면 어셈블리와 같은 디렉터리에는 지원 하 고이.xml 파일을 추가 하려는 어셈블리와 동일 하 게 하는.xml 파일의 파일 이름을 확인 합니다. Visual Studio 프로젝트에 어셈블리 참조 되는.xml 파일을 찾을 됩니다. 자세한 내용은 참조 [IntelliSense를 사용 하 여](/visualstudio/ide/using-intellisense) 및 [XML 코드 주석 제공](/visualstudio/ide/supplying-xml-code-comments)합니다.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.  
  
2.  확장 된 **구성 속성** 노드.  
  
3.  확장 된 **C/c + +** 노드.  
  
4.  선택 된 **출력 파일** 속성 페이지.  
  
5.  수정 된 **XML 문서 파일 생성** 속성입니다.  
  
### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
1.  <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.GenerateXMLDocumentationFiles%2A>을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)