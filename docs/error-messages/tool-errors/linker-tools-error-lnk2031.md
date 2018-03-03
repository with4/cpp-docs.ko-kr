---
title: "링커 도구 오류 LNK2031 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK2031
dev_langs:
- C++
helpviewer_keywords:
- LNK2031
ms.assetid: 18ed4b6e-3e75-443c-bbd8-2f6030dc89ee
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2a519b4241c9ffabaeeb387cc8e4997125d57781
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk2031"></a>링커 도구 오류 LNK2031
"function_declaration" decorated_name;에 대 한 p/invoke를 생성할 수 없습니다. 메타 데이터에 누락 된 호출 규칙  
  
 순수 이미지에는 네이티브 함수 가져오기에 유의 해야 하는 동안 네이티브 및 순수 컴파일 간에 암시적 호출 규칙이 다릅니다. 순수 이미지에 대 한 자세한 내용은 참조 [순수형 및 안정형 코드 (C + + /cli CLI)](../../dotnet/pure-and-verifiable-code-cpp-cli.md)합니다.  
  
## <a name="example"></a>예  
 이 코드 샘플에서는 구성 요소를 해당 호출 규칙을 암시적으로 지정 하 고 내보낸된 네이티브 함수로 [__cdecl](../../cpp/cdecl.md)합니다.  
  
```  
// LNK2031.cpp  
// compile with: /LD  
extern "C" {  
   __declspec(dllexport) int func() { return 3; }  
};  
```  
  
## <a name="example"></a>예  
 다음 샘플 네이티브 함수를 사용 하는 순수 클라이언트를 만듭니다. 그러나 경우 호출 규칙 **/clr: pure** 은 [__clrcall](../../cpp/clrcall.md)합니다. 다음 샘플에서는 LNK2031 합니다.  
  
```  
// LNK2031_b.cpp  
// compile with: /clr:pure LNK2031.lib  
// LNK2031 expected  
extern "C" int func();  
  
int main() {  
   return func();  
}  
```  
  
## <a name="example"></a>예  
 다음 예제에는 순수 이미지에서 네이티브 함수를 사용 하는 방법을 보여 줍니다. 명시적 참고 **__cdecl** 호출 규칙 지정 자가 있습니다.  
  
```  
// LNK2031_c.cpp  
// compile with: /clr:pure LNK2031.lib  
extern "C" int __cdecl func();  
  
int main() {  
   return func();  
}  
```