---
title: -(코 지원 활성화) await | Microsoft Docs
ms.custom: ''
ms.date: 08/15/2017
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /await
- -await
dev_langs:
- C++
helpviewer_keywords:
- /await enable coroutine support [C++]
- -await enable coroutine support [C++]
- await enable coroutine support [C++]
ms.assetid: 302c8e69-09b6-4c58-bcdd-0a6a8713a8df
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 78a62195ca28be49ed8c00dacacce003281699f9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="await-enable-coroutine-support"></a>/await (코 지원 사용)  
  
사용 하 여는 **/await** 컴파일러 옵션 코 루틴에 대 한 컴파일러 지원을 사용 하도록 설정 합니다.  
  
## <a name="syntax"></a>구문  
  
> await /  
  
## <a name="remarks"></a>설명  
  
**/await** 컴파일러 옵션을 사용 하면 c + + 코 루틴 및 키워드에 대 한 컴파일러 지원 **co_await**, **co_yield**, 및 **co_return**. 이 옵션은 기본적으로 해제되어 있습니다. Visual Studio에서 코 루틴에 대 한 지원에 대 한 정보를 참조 하십시오.는 [Visual Studio 팀 블로그](https://blogs.msdn.microsoft.com/vcblog/category/coroutine/)합니다. 코 루틴 표준 제안에 대 한 자세한 내용은 참조 [N4628 작업 초안, 코 루틴에 대 한 c + + 확장에 대 한 기술 사양](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/n4628.pdf)합니다.  

**/await** 옵션은 Visual Studio 2015부터 사용할 수 있습니다.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1. 프로젝트의를 열고 **속성 페이지** 대화 상자.   
  
2. **구성 속성**, 확장 하 고는 **C/c + +** 폴더를 선택 하 고는 **명령줄** 속성 페이지.  
  
3. 입력의 **/await** 컴파일러 옵션에는 **추가 옵션** 상자. 선택 **확인** 또는 **적용** 변경 내용을 저장 합니다.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
  
[컴파일러 옵션](../../build/reference/compiler-options.md)   
[컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)