---
title: "링커 도구 오류 LNK1313 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK1313
dev_langs: C++
helpviewer_keywords: LNK1313
ms.assetid: 5df0b72e-bb3f-428c-8d84-6084238f9827
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a9030921178fc23c225a775359724cf5c932d95e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk1313"></a>링커 도구 오류 LNK1313
ijw/native 모듈이 발견되었습니다. 순수 모듈에 링크할 수 없습니다.  
  
 현재 버전의 Visual c + + 네이티브 또는 혼합 관리/네이티브.obj 파일을 사용 하 여 컴파일된.obj 파일에 연결을 지원 하지 않습니다 **/clr: pure**합니다.  
  
## <a name="example"></a>예  
  
```  
// LNK1313.cpp  
// compile with: /c /clr:pure  
// a pure module  
int main() {}  
```  
  
## <a name="example"></a>예  
  
```  
// LNK1313_b.cpp  
// compile with: /c /clr  
// an IJW module  
void test(){}  
```  
  
## <a name="example"></a>예  
 다음 샘플에서는 LNK1313을 생성합니다.  
  
```  
// LNK1313_c.cpp  
// compile with: /link LNK1313.obj LNK1313_b.obj  
// LNK1313 warning expected  
```