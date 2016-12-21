---
title: "방법: 바이트 배열에 대한 포인터 가져오기 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "바이트 배열"
  - "포인터, 바이트 배열"
ms.assetid: aea18073-3341-47f4-9f0e-04e03327037e
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: 바이트 배열에 대한 포인터 가져오기
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

첫 번째 인수의 주소를 가져오고 이를 포인터에 할당하여 <xref:System.Byte> 배열에서 배열 블록에 대한 포인터를 가져올 수 있습니다.  
  
## 예제  
  
```  
// pointer_to_Byte_array.cpp  
// compile with: /clr  
using namespace System;  
int main() {  
   Byte bArr[] = {1, 2, 3};  
   Byte* pbArr = &bArr[0];  
  
   array<Byte> ^ bArr2 = gcnew array<Byte>{1,2,3};  
   interior_ptr<Byte> pbArr2 = &bArr2[0];  
}  
```  
  
## 참고 항목  
 [C\+\+ Interop 사용\(암시적 PInvoke\)](../dotnet/using-cpp-interop-implicit-pinvoke.md)