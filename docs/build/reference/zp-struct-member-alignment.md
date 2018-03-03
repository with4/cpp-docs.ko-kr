---
title: "-Zp (구조체 멤버 맞춤) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /zp
- VC.Project.VCCLCompilerTool.StructMemberAlignment
- VC.Project.VCCLWCECompilerTool.StructMemberAlignment
dev_langs:
- C++
helpviewer_keywords:
- Struct Member Alignment compiler option
- Zp compiler option
- /Zp compiler option [C++]
- -Zp compiler option [C++]
ms.assetid: 5242f656-ed9b-48a3-bc73-cfcf3ed2520f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4d387e0ab020e96afb3e2975b5c8686b668cbc10
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="zp-struct-member-alignment"></a>/Zp(구조체 멤버 맞춤)
구조체의 멤버를 메모리에 압축 되는 방식을 제어 하 고 모듈의 모든 구조에 대해 동일한 압축을 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
/Zp[1|2|4|8|16]  
```  
  
## <a name="remarks"></a>설명  
 이 옵션을 지정 된 멤버 형식의 크기에는 첫 번째 이후 각 구조체 멤버가 저장 됩니다 또는 `n`-바이트 경계 (여기서 `n` 는 1, 2, 4, 8 또는 16), 중 더 작은 값입니다.  
  
 사용 가능한 값은 다음 표에 설명 되어 있습니다.  
  
 1  
 1 바이트 경계에서 구조체를 압축 합니다. 와 동일 **/Zp**합니다.  
  
 2  
 2 바이트 경계에서 구조체를 압축 합니다.  
  
 4  
 4 바이트 경계에서 구조체를 압축 합니다.  
  
 8  
 (기본값) 8 바이트 경계에서 구조체를 압축 합니다.  
  
 16  
 16 바이트 경계에서 구조체를 압축 합니다.  
  
 특정 맞춤 요구 사항이 있는 아니라면이 옵션을 사용 하지 않아야 합니다.  
  
 사용할 수도 있습니다 [팩](../../preprocessor/pack.md) 제어 구조 했음입니다. 정렬에 대한 자세한 내용은 다음을 참조하십시오.  
  
-   [align](../../cpp/align-cpp.md)  
  
-   [__alignof 연산자](../../cpp/alignof-operator.md)  
  
-   [__unaligned](../../cpp/unaligned.md)  
  
-   [구조체 맞춤 예제](../../build/examples-of-structure-alignment.md) (x64 전용)  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.  
  
2.  **C/C++** 폴더를 클릭합니다.  
  
3.  클릭는 **코드 생성** 속성 페이지.  
  
4.  수정 된 **구조체 멤버 맞춤** 속성입니다.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.StructMemberAlignment%2A>을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)