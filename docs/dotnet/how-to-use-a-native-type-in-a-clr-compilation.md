---
title: "방법: 네이티브 형식-clr 컴파일에서 사용 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs:
- C++
helpviewer_keywords:
- compilation, native types in /clr
- /clr compiler option [C++], using native types
ms.assetid: 3a505c90-4adb-4942-9cf9-7d1fdcbc01e7
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: c0a73d5bd9c165645dbf3c3cdee7a740cc3c16a3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-use-a-native-type-in-a-clr-compilation"></a>방법: /clr 컴파일에 네이티브 형식 사용
네이티브 형식을 정의할 수 있습니다는 **/clr** 컴파일 및 어셈블리 내에서 네이티브 형식을 사용 되는 모든는 유효 합니다. 그러나 네이티브 형식은 참조 된 메타 데이터에서 사용 하기 위해 사용할 수 없습니다.  
  
 각 어셈블리를 사용 합니다 모든 네이티브 형식의 정의 포함 해야 합니다.  
  
 자세한 내용은 [/clr(공용 언어 런타임 컴파일)](../build/reference/clr-common-language-runtime-compilation.md)을 참조하세요.  
  
## <a name="example"></a>예  
 이 샘플에서는 정의 하 고 네이티브 형식을 사용 하는 구성 요소를 만듭니다.  
  
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
  
## <a name="example"></a>예  
 이 샘플에서는 구성 요소를 사용 하는 클라이언트를 정의 합니다. 컴파일 대상에 정의 되어 있지 않으면 네이티브 형식에 액세스 오류 인지를 확인 합니다.  
  
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
  
## <a name="see-also"></a>참고 항목  
 [C++ Interop 사용(암시적 PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)