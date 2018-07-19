---
title: -Qfast_transcendentals (빠른 초월수 강제) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /Qfast_transcendentals
dev_langs:
- C++
helpviewer_keywords:
- /Qfast_transcendentals
- Force Fast Transcendentals
ms.assetid: 4de24bd1-38e6-49d4-9a05-04c9937d24ac
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c4bb296c8a1fdfde46969ef601fde33c901c9306
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32377432"
---
# <a name="qfasttranscendentals-force-fast-transcendentals"></a>/Qfast_transcendentals(빠른 초월수 강제 적용)
초월수 함수에 대 한 인라인 코드를 생성합니다.  
  
## <a name="syntax"></a>구문  
  
```  
/Qfast_transcendentals  
```  
  
## <a name="remarks"></a>설명  
 이 컴파일러 옵션은 초월수 함수를 인라인 코드 실행 속도 개선 하기 위해 변환할 수 있습니다. 이 옵션은 영향을 함께 사용 하는 경우에 **/fp: 제외한** 또는 **/fp: 정확한**합니다. 초월수 함수에 대 한 인라인 코드를 생성 하는 기본 동작에서 이미 **/fp: fast**합니다.  
  
 이 옵션와 호환 되지 않습니다. **/fp: strict**합니다. 참조 [/fp (부동 소수점 동작 지정)](../../build/reference/fp-specify-floating-point-behavior.md) 부동 소수점 컴파일러 옵션에 대 한 자세한 내용은 합니다.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.  
  
2.  **C/C++** 폴더를 클릭합니다.  
  
3.  **명령줄** 속성 페이지를 클릭합니다.  
  
4.  **추가 옵션** 상자에 컴파일러 옵션을 입력합니다.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [/Q 옵션 (하위 수준 작업)](../../build/reference/q-options-low-level-operations.md)   
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)