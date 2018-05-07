---
title: 링커 도구 오류 LNK1237 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1237
dev_langs:
- C++
helpviewer_keywords:
- LNK1237
ms.assetid: 8722ffa8-096a-4bb0-85f9-f3aa0e10872a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1ffc337d6b1548db4717dc4b87ff8aa25ef92e93
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-error-lnk1237"></a>링커 도구 오류 LNK1237
코드를 생성 하는 동안 컴파일러 'symbol' /GL으로 컴파일된 ' module' 모듈에 정의 된 기호 참조를 했습니다.  
  
 코드를 생성 하는 동안 컴파일러 파생 시킬 수 없습니다 이후에 컴파일된 정의로 확인 되는 기호 **/GL**합니다. `symbol` 가 도입 되어 나중에 사용 하 여 컴파일된 정의로 확인 된 기호 **/GL**합니다.  
  
 자세한 내용은 [/GL(전체 프로그램 최적화)](../../build/reference/gl-whole-program-optimization.md)을 참조하세요.  
  
 LNK1237를 해결 하려면 컴파일하지 않는 기호 너비 **/GL** 사용 또는 [/INCLUDE (강제 기호 참조)](../../build/reference/include-force-symbol-references.md) 기호에 대 한 참조를 되도록 합니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 lnk1237 오류가 발생 합니다. 이 오류를 해결 하려면 하지 LNK1237_a.cpp 배열을 초기화 않으며 추가 **/include: __chkstk** 링크 명령입니다.  
  
```  
// LNK1237_a.cpp  
int main() {  
   char c[5000] = {0};  
}  
```  
  
```  
// LNK1237_b.cpp  
// compile with: /GS- /GL /c LNK1237_a.cpp  
// processor: x86  
// post-build command: (lib LNK1237_b.obj /LTCG & link LNK1237_a.obj LNK1237_b.lib /nodefaultlib /entry:main /LTCG)  
extern "C" void _chkstk(size_t s) {}  
```