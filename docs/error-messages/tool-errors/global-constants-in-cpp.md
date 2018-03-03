---
title: "C + +의 전역 상수 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
dev_langs:
- C++
helpviewer_keywords:
- global constants
- constants, global
ms.assetid: df5a9bd4-d0a8-4c1c-956e-b481d0bded7d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 766e1a6f48ecf3f64110e64d916c50d92c89345d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="global-constants-in-c"></a>C++의 전역 상수
C + +의 전역 상수는 고정 링크가 있습니다. 3. 다릅니다. 전역 사용 하려고 하면 여러 파일의 c + +에서 상수 오류가 해결 되지 않은 외부 합니다. 컴파일러는 변수에 대 한 예약 된 공간이 없습니다 out, 전역 상수를 최적화 합니다.  
  
 이 오류를 해결 하는 한 가지 방법은 const 초기화 헤더 파일에 포함할를 함수 프로토타입에서 마찬가지로, 필요한 경우를 CPP 파일에 해당 헤더를 포함 하는 것입니다. 또 다른 원인은 변수를 비상수 것을 평가할 때 상수 참조를 사용 합니다.  
  
 다음 샘플에서는 C2019 오류가 생성 됩니다.  
  
```  
// global_constants.cpp  
// LNK2019 expected  
void test(void);  
const int lnktest1 = 0;  
  
int main() {  
   test();  
}  
```  
  
 그리고  
  
```  
// global_constants_2.cpp  
// compile with: global_constants.cpp  
extern int lnktest1;  
  
void test() {  
  int i = lnktest1;   // LNK2019  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [링커 도구 오류 LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md)