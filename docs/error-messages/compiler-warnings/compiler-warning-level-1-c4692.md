---
title: "컴파일러 경고 (수준 1) C4692 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4692
dev_langs: C++
helpviewer_keywords: C4692
ms.assetid: f6fb3acc-8228-491a-9c30-ce302d8a9c75
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8088c1434ab33899f60b08c0817464f9ddb9c82e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4692"></a>컴파일러 경고(수준 1) C4692
'function': 전용이 아닌 멤버의 시그니처에 어셈블리 전용 네이티브 형식 'native_type'이(가) 있습니다.  
  
 어셈블리 외부에 표시 되는 형식의 멤버 함수는 어셈블리 외부에 표시 되지 않는 네이티브 형식이 포함 된 시그니처를 포함 합니다. 따라서 포함 하는 형식이 어셈블리 외부에서 인스턴스화할 경우이 멤버 함수를 호출 하지 해야 합니다.  
  
 자세한 내용은 참조 [표시 유형 입력](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Type_visibility)합니다.  
  
 기본적으로 이 경고는 해제되어 있습니다. 자세한 내용은 [Compiler Warnings That Are Off by Default](../../preprocessor/compiler-warnings-that-are-off-by-default.md)을 참조하세요.  
  
## <a name="example"></a>예  
 다음 샘플에서는 C4692 경고가 발생 합니다.  
  
```  
// C4692.cpp  
// compile with: /W1 /c /clr  
#pragma warning(default:4692)  
class Private_Native_Class {};  
public class Public_Native_Class {};  
public ref class Public_Ref_Class {  
public:  
   void Test(Private_Native_Class *) {}   // C4692  
   void Test2(Public_Native_Class *) {}   // OK  
};  
```