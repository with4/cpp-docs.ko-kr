---
title: "방법: /clr 컴파일에 네이티브 형식 사용 | Microsoft Docs"
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
  - "/clr 컴파일러 옵션[C++], 네이티브 형식 사용"
  - "컴파일, /clr에 네이티브 형식 사용"
ms.assetid: 3a505c90-4adb-4942-9cf9-7d1fdcbc01e7
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: /clr 컴파일에 네이티브 형식 사용
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**\/clr** 컴파일에서 네이티브 형식을 정의하고 어셈블리 내에서 이 네이티브 형식을 임의로 사용할 수 있습니다.  그러나 참조된 메타데이터에서 사용할 용도로는 네이티브 형식이 지원되지 않습니다.  
  
 각 어셈블리에는 사용할 모든 네이티브 형식에 대한 정의가 포함되어야 합니다.  
  
 자세한 내용은 [\/clr\(공용 언어 런타임 컴파일\)](../build/reference/clr-common-language-runtime-compilation.md)을 참조하십시오.  
  
## 예제  
 이 샘플에서는 네이티브 형식을 정의하고 사용하는 구성 요소를 만듭니다.  
  
```  
// use_native_type_in_clr.cpp  
// compile with: /clr /LD  
public struct NativeClass {  
   static int Test() { return 98; }  
};  
  
public ref struct ManagedClass {  
   static int i = NativeClass::Test();  
   void Test() {  
      System::Console::WriteLine(i);  
   }  
};  
```  
  
## 예제  
 이 샘플에서는 구성 요소를 사용하는 클라이언트를 정의합니다.  컴파일 대상에 정의되지 않은 네이티브 형식에 액세스하려고 하면 오류가 발생합니다.  
  
```  
// use_native_type_in_clr_2.cpp  
// compile with: /clr  
#using "use_native_type_in_clr.dll"  
// Uncomment the following 3 lines to resolve.  
// public struct NativeClass {  
//    static int Test() { return 98; }  
// };  
  
int main() {  
   ManagedClass x;  
   x.Test();  
  
   System::Console::WriteLine(NativeClass::Test());   // C2653  
}  
```  
  
## 참고 항목  
 [C\+\+ Interop 사용\(암시적 PInvoke\)](../dotnet/using-cpp-interop-implicit-pinvoke.md)