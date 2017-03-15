---
title: "컴파일러 경고 (수준 1) C4397 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4397"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4397"
ms.assetid: 6346fdc2-dbbf-4fba-803a-32b0d0a707be
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 경고 (수준 1) C4397
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

DefaultCharSetAttribute가 무시됩니다.  
  
 <xref:System.Runtime.InteropServices.DefaultCharSetAttribute>는 Visual C\+\+ 컴파일러에서 무시됩니다.  DLL에 대한 문자 집합을 지정하려면 DllImport의 CharSet 옵션을 사용해야 합니다.  자세한 내용은 [C\+\+ Interop 사용\(암시적 PInvoke\)](../../dotnet/using-cpp-interop-implicit-pinvoke.md)을 참조하십시오.  
  
## 예제  
 다음 샘플에서는 C4397 경고가 발생하는 경우를 보여 줍니다.  
  
```  
// C4397.cpp  
// compile with: /W1 /c /clr  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
[module:DefaultCharSetAttribute(CharSet::Unicode)];   // C4397  
  
[DllImport("kernel32", EntryPoint="CloseHandle", CharSet=CharSet::Unicode)]   // OK  
extern "C" bool ImportDefault(IntPtr hObject);  
  
public ref class MySettingVC {  
public:  
   void method() {  
      ImportDefault(IntPtr::Zero);  
   }  
};  
  
[StructLayout(LayoutKind::Explicit)]  
public ref struct StructDefault1{};  
  
public ref class ClassDefault1{};  
```