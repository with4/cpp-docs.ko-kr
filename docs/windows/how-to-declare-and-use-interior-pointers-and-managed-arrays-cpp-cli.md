---
title: "방법: 선언 및 내부 포인터 및 관리 되는 배열 사용 (C + + /cli CLI) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- pointers, interior
- arrays [C++], managed
ms.assetid: e61a2c09-a7d0-4867-91ea-6b8788a01079
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: caa0c3cc2c379362972d1b24e80f3ebb94d9f878
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-declare-and-use-interior-pointers-and-managed-arrays-ccli"></a>방법: 내부 포인터 및 관리되는 배열 선언 및 사용(C++/CLI)
다음 C + + /cli CLI 샘플 선언 배열에 내부 포인터를 사용 하는 방법을 보여 줍니다.  
  
> [!IMPORTANT]
>  이 언어 기능으로 사용할 수는 **/clr** 컴파일러 옵션을 하지만 하지는 **/ZW** 컴파일러 옵션입니다.  
  
## <a name="example"></a>예  
  
### <a name="code"></a>코드  
  
```  
// interior_ptr_arrays.cpp  
// compile with: /clr  
#define SIZE 10  
  
int main() {  
   // declare the array  
   array<int>^ arr = gcnew array<int>(SIZE);  
  
   // initialize the array  
   for (int i = 0 ; i < SIZE ; i++)  
      arr[i] = i + 1;  
  
   // create an interior pointer into the array  
   interior_ptr<int> ipi = &arr[0];  
  
   System::Console::WriteLine("1st element in arr holds: {0}", arr[0]);  
   System::Console::WriteLine("ipi points to memory address whose value is: {0}", *ipi);  
  
   ipi++;  
   System::Console::WriteLine("after incrementing ipi, it points to memory address whose value is: {0}", *ipi);  
}  
```  
  
### <a name="output"></a>출력  
  
```  
1st element in arr holds: 1  
ipi points to memory address whose value is: 1  
after incrementing ipi, it points to memory address whose value is: 2  
```  
  
## <a name="see-also"></a>참고 항목  
 [interior_ptr(C++/CLI)](../windows/interior-ptr-cpp-cli.md)