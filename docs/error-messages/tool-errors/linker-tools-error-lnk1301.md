---
title: 링커 도구 오류 LNK1301 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1301
dev_langs:
- C++
helpviewer_keywords:
- LNK1301
ms.assetid: 760da428-7182-4b25-b20a-de90d4b9a9cd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0b4e298ad3815c741ff6c901ac39bf7838ed135d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-error-lnk1301"></a>링커 도구 오류 LNK1301
LTCG clr 모듈이 /LTCG:parameter 호환 되지 않습니다.  
  
 /Clr 및 /GL으로 컴파일한 모듈 /LTCG의 (PGO) 매개 변수는 프로필 기반 최적화 중 하 나와 함께 링커로 전달 되었습니다.  
  
 프로필 기반 최적화 /clr 모듈에 지원 되지 않습니다.  
  
 자세한 내용은 다음을 참조하세요.  
  
-   [/GL(전체 프로그램 최적화)](../../build/reference/gl-whole-program-optimization.md)  
  
-   [/LTCG(링크 타임 코드 생성)](../../build/reference/ltcg-link-time-code-generation.md)  
  
-   [/clr(공용 언어 런타임 컴파일)](../../build/reference/clr-common-language-runtime-compilation.md)  
  
-   [프로필 기반 최적화](../../build/reference/profile-guided-optimizations.md)  
  
### <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1.  /Clr으로 컴파일하지 않습니다 또는 /LTCG을 PGO 매개 변수 중 하나에 연결 하지 마십시오.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 LNK1301 오류가 생성 됩니다.  
  
```  
// LNK1301.cpp  
// compile with: /clr /GL /link /LTCG:PGI LNK1301.obj  
// LNK1301 expected  
class MyClass {  
public:  
   int i;  
};  
```