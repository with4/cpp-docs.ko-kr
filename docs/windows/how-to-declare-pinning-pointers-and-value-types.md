---
title: '방법: 고정 포인터를 선언 및 값 형식 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- value types, declaring
- pinning pointers
ms.assetid: 57c5ec8a-f85a-48c4-ba8b-a81268bcede0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9c2dbb4bcbd1b6c76d00356535a9c99d983c1096
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40019880"
---
# <a name="how-to-declare-pinning-pointers-and-value-types"></a>방법: 고정 포인터 및 값 형식 선언
값 형식은 암시적으로 boxing할 수 있습니다. 자체 및 사용에 다음 값 형식 개체에 대 한 고정 포인터를 선언할 수 있습니다는 **pin_ptr** boxed 값 형식입니다.  
  
## <a name="example"></a>예  
  
### <a name="code"></a>코드  
  
```cpp  
// pin_ptr_value.cpp  
// compile with: /clr  
value struct V {  
   int i;  
};  
  
int main() {  
   V ^ v = gcnew V;   // imnplicit boxing  
   v->i=8;  
   System::Console::WriteLine(v->i);  
   pin_ptr<V> mv = &*v;  
   mv->i = 7;  
   System::Console::WriteLine(v->i);  
   System::Console::WriteLine(mv->i);  
}  
```  
  
```Output  
8  
7  
7  
```  
  
## <a name="see-also"></a>참고 항목  
 [pin_ptr(C++/CLI)](../windows/pin-ptr-cpp-cli.md)