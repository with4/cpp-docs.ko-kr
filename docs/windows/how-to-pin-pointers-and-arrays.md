---
title: '방법: 포인터 및 배열 고정 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- pointers, pinning
- arrays [C++], pinning
ms.assetid: ee783260-e676-46b8-a38e-11a06f1d57b0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b1cea9b1c7c6738c33f00e984aa8212d611b4aec
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33873591"
---
# <a name="how-to-pin-pointers-and-arrays"></a>방법: 포인터 및 배열 고정
관리되는 개체에 정의된 하위 개체를 고정하면 전체 개체를 고정하는 효과가 있습니다.  예를 들어, 모든 배열 요소가 고정되어 있는 경우 전체 배열도 고정됩니다. 고정된 배열을 선언하기 위한 언어 확장은 없습니다. 배열을 고정하려면 해당 요소 형식에 대한 고정 포인터를 선언하고 이러한 요소 중 하나를 고정합니다.  
  
## <a name="example"></a>예제  
  
### <a name="code"></a>코드  
  
```  
// pin_ptr_array.cpp  
// compile with: /clr  
#include <stdio.h>  
using namespace System;  
  
int main() {  
   array<Byte>^ arr = gcnew array<Byte>(4);  
   arr[0] = 'C';  
   arr[1] = '+';  
   arr[2] = '+';  
   arr[3] = '\0';  
   pin_ptr<Byte> p = &arr[1];   // entire array is now pinned  
   unsigned char * cp = p;  
  
   printf_s("%s\n", cp); // bytes pointed at by cp  
                         // will not move during call  
}  
```  
  
### <a name="output"></a>출력  
  
```  
++  
```  
  
## <a name="see-also"></a>참고 항목  
 [pin_ptr(C++/CLI)](../windows/pin-ptr-cpp-cli.md)