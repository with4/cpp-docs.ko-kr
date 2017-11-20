---
title: "컴파일러 경고 (수준 1) C4397 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4397
dev_langs: C++
helpviewer_keywords: C4397
ms.assetid: 6346fdc2-dbbf-4fba-803a-32b0d0a707be
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 85d15a25bf55bcc63f0506d74cf4268290c60905
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4397"></a>컴파일러 경고(수준 1) C4397
DefaultCharSetAttribute는 무시 됩니다.  
  
 <xref:System.Runtime.InteropServices.DefaultCharSetAttribute>Visual c + + 컴파일러에서 무시 됩니다. 문자는 DLL에 대 한 집합을 지정 하려면 DllImport의 문자 집합 옵션을 사용 합니다. 자세한 내용은 참조 [c + + Interop를 사용 하 여 (암시적 PInvoke)](../../dotnet/using-cpp-interop-implicit-pinvoke.md)합니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C4397 경고가 발생 합니다.  
  
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