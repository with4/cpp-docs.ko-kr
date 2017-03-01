---
title: "컴파일러 오류 C2728 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2728
dev_langs:
- C++
helpviewer_keywords:
- C2728
ms.assetid: 65635f91-1cd1-46e4-9ad7-14726d0546af
caps.latest.revision: 17
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: c243063a9770542f137d5950e8a269f771960f74
ms.openlocfilehash: 4e28f463dffeda0bc1b44da4d4e228771f59cc4c
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2728"></a>컴파일러 오류 C2728
'type' : 네이티브 배열은 이러한 형식을 포함할 수 없습니다.  
  
 배열 생성 구문을 사용하여 관리되는 개체 또는 WinRT 개체를 만들었습니다. 관리되는 개체 또는 WinRT 개체의 배열은 네이티브 배열 구문을 사용하여 만들 수 없습니다.  
  
 자세한 내용은 참조 [배열](../../windows/arrays-cpp-component-extensions.md)합니다.  
  
 다음 샘플에서는 C2728 오류가 발생하는 경우 및 이를 해결하는 방법을 보여 줍니다.  
  
```  
// C2728.cpp  
// compile with: /clr  
  
int main() {  
   int^ arr[5];   // C2728  
  
   // try the following line instead  
   array<int>^arr2;  
}  
```  

