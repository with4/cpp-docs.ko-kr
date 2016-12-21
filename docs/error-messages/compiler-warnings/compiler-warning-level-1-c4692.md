---
title: "컴파일러 경고(수준 1) C4692 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4692"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4692"
ms.assetid: f6fb3acc-8228-491a-9c30-ce302d8a9c75
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고(수준 1) C4692
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function': 전용이 아닌 멤버의 시그니처에 어셈블리 전용 네이티브 형식 'native\_type'이\(가\) 있습니다.  
  
 어셈블리 외부에서 표시되지 않는 네이티브 형식이 해당 시그니처에 들어 있는 멤버 함수가 어셈블리 외부에서 표시되는 형식에 포함되어 있습니다.  따라서 해당 포함 형식이 어셈블리 외부에서 인스턴스화되지 않으면 이 멤버 함수를 호출할 수 없습니다.  
  
 자세한 내용은 [형식 표시](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Type_visibility)을 참조하십시오.  
  
 이 경고는 기본적으로 해제되어 있습니다.  자세한 내용은 [기본적으로 해제되어 있는 컴파일러 경고](../../preprocessor/compiler-warnings-that-are-off-by-default.md)을 참조하십시오.  
  
## 예제  
 다음 샘플에서는 C4692 경고가 발생하는 경우를 보여 줍니다.  
  
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