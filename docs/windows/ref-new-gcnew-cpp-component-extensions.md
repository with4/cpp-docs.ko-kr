---
title: "ref new, gcnew  (C++ Component Extensions) | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "gcnew"
  - "ref new"
  - "gcnew_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ref new keyword (C++)"
  - "gcnew keyword [C++]"
ms.assetid: 388a62da-c2df-4a94-a9a2-205b53e577da
caps.latest.revision: 24
caps.handback.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ref new, gcnew  (C++ Component Extensions)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`ref new` 집계 키워드는 개체에 액세스할 수 없을 때 수집되는 가비지인 형식의 인스턴스를 할당하며 할당된 개체에 핸들\([^](../windows/handle-to-object-operator-hat-cpp-component-extensions.md)\)을 반환합니다.  
  
## 모든 런타임  
 `ref new`에서 할당한 형식의 인스턴스에 대한 메모리가 자동으로 할당 취소됩니다.  
  
 메모리를 할당할 수 없는 경우 `ref new` 작업에서 `OutOfMemoryException`이 throw됩니다.  
  
 네이티브 C\+\+ 형식에 대한 메모리가 할당되고 할당 취소되는 방법에 대한 자세한 내용은 [new 및 delete 연산자](../cpp/new-and-delete-operators.md)를 참조하세요.  
  
## [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]  
 `ref new`를 사용하여 수명을 자동으로 관리하려는 Windows 런타임 개체에 대한 메모리를 할당할 수 있습니다.  참조 개수가 0이 되면 개체는 자동으로 할당 취소되며, 참조의 마지막 복사본이 범위를 벗어난 후에 발생합니다.  자세한 내용은 [Ref 클래스 및 구조체](http://msdn.microsoft.com/library/windows/apps/hh699870.aspx)를 참조하세요.  
  
### 요구 사항  
 컴파일러 옵션: **\/ZW**  
  
## [!INCLUDE[clr_for_headings](../dotnet/includes/clr_for_headings_md.md)]  
 관리되는 형식\(참조 또는 값 형식\)에 대한 메모리는 `gcnew`에 의해 할당되고 가비지 수집을 사용하여 할당 취소됩니다.  
  
### 요구 사항  
 컴파일러 옵션: **\/clr**  
  
### 예  
 **예제**  
  
 다음 예제에서는 `gcnew`를 사용하여 Message 개체를 할당합니다.  
  
```  
// mcppv2_gcnew_1.cpp  
// compile with: /clr  
ref struct Message {  
   System::String^ sender;  
   System::String^ receiver;  
   System::String^ data;  
};  
  
int main() {  
   Message^ h_Message  = gcnew Message;  
  //...  
}  
```  
  
 **예제**  
  
 다음 예제에서는 `gcnew`를 사용하여 참조 형식처럼 사용할 boxed 값 형식을 만듭니다.  
  
```  
// example2.cpp : main project file.  
// compile with /clr  
using namespace System;  
value class Boxed {  
    public:  
        int i;  
};  
int main()  
{  
    Boxed^ y = gcnew Boxed;  
    y->i = 32;  
    Console::WriteLine(y->i);  
    return 0;  
}  
```  
  
 **출력**  
  
  **32**   
## 참고 항목  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)