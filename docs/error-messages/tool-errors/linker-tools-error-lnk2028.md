---
title: 링커 도구 오류 LNK2028 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK2028
dev_langs:
- C++
helpviewer_keywords:
- LNK2028
ms.assetid: e2b03293-6066-464d-a050-ce747bcf7f0e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7347e8edda7ad8b317d4e6e02dfc9345ac76f269
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-error-lnk2028"></a>링커 도구 오류 LNK2028
"exported_function" (decorated_name) 함수 "function_containing_function_call" (decorated_name)에서 참조  
  
 순수 이미지에는 네이티브 함수 가져오기에 유의 해야 하는 동안 네이티브 및 순수 컴파일 간에 암시적 호출 규칙이 다릅니다.  
  
## <a name="example"></a>예제  
 이 코드 샘플에서는 구성 요소를 해당 호출 규칙을 암시적으로 지정 하 고 내보낸된 네이티브 함수로 [__cdecl](../../cpp/cdecl.md)합니다.  
  
```  
// LNK2028.cpp  
// compile with: /LD  
__declspec(dllexport) int func() {  
   return 3;  
}  
```  
  
## <a name="example"></a>예제  
 다음 샘플 네이티브 함수를 사용 하는 순수 클라이언트를 만듭니다. 그러나 경우 호출 규칙 **/clr: pure** 은 [__clrcall](../../cpp/clrcall.md)합니다. 다음 샘플에서는 LNK2028 합니다.  
  
```  
// LNK2028_b.cpp  
// compile with: /clr:pure lnk2028.lib  
// LNK2028 expected  
int func();  
  
int main() {  
   return func();  
}  
```