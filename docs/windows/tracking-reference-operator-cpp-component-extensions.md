---
title: "Tracking Reference Operator (C++ Component Extensions) | Microsoft Docs"
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
  - "%"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "tracking references"
  - "% tracking reference [C++]"
ms.assetid: 142a7269-ab69-4b54-a6d7-833bef06228f
caps.latest.revision: 31
caps.handback.revision: 29
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Tracking Reference Operator (C++ Component Extensions)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

*추적 참조*\(`%`\)는 일반 C\+\+ 참조\(`&`\)처럼 동작하지만, 예외적으로 개체를 추적 참조에 할당한 경우는 개체 참조 개수가 증가합니다.  
  
## 모든 플랫폼  
 추적 참조에는 다음과 같은 특징이 있습니다.  
  
-   개체를 추적 참조에 할당하면 개체 참조 개수가 증가합니다.  
  
-   네이티브 참조\(&\)는 \*를 역참조할 경우의 결과입니다.  추적 참조\(%\)는 ^를 역참조할 경우의 결과입니다.  개체에 %가 있을 경우 해당 개체는 메모리에 유지됩니다.  
  
-   개체 멤버에 액세스하는 데 점\(`.`\) 멤버 액세스 연산자가 사용됩니다.  
  
-   추적 참조는 값 형식 및 핸들에만 유효합니다\(예: `String^`\).  
  
-   추적 참조는 null 또는 `nullptr` 값에 할당할 수 없습니다.  추적 참조는 필요한 횟수만큼 유효한 다른 개체에 다시 할당할 수 있습니다.  
  
-   추적 참조는 단항 주소 연산자로 사용할 수 없습니다.  
  
## [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]  
 추적 참조는 %가 참조 개수를 계산한다는 점을 제외하면 표준 C\+\+ 참조처럼 동작합니다.  다음 코드 조각에서는 % 형식과 ^ 형식을 변환하는 방법을 보여 줍니다.  
  
```  
Foo^ spFoo = ref new Foo();  
Foo% srFoo = *spFoo;  
Foo^ spFoo2 = %srFoo;  
```  
  
 다음 예제에서는 %를 사용하는 함수에 ^를 전달하는 방법을 보여 줍니다.  
  
```  
  
ref class Foo sealed {};  
  
    // internal or private  
    void UseFooHelper(Foo% f)  
    {  
        auto x = %f;  
    }  
  
    // public method on ABI boundary  
    void UseFoo(Foo^ f)  
    {  
        if (f != nullptr) { UseFooHelper(*f); }  
    }  
  
```  
  
## [!INCLUDE[clr_for_headings](../dotnet/includes/clr_for_headings_md.md)]  
 C\+\+\/CLI에서는 가비지 수집 힙에 있는 CLR 형식의 개체에 바인딩할 경우 핸들에 대해 추적 참조를 사용할 수 있습니다.  
  
 CLR에서는 가비지 수집기가 참조 개체를 이동할 때마다 추적 참조 변수의 값이 자동으로 업데이트됩니다.  
  
 추적 참조는 스택에서만 선언할 수 있습니다.  추적 참조는 클래스의 멤버일 수 없습니다.  
  
 가비지 수집 힙에서는 개체에 대한 네이티브 C\+\+ 참조를 사용할 수 없습니다.  
  
 C\+\+\/CLI의 추적 참조에 대한 자세한 내용은 다음을 참조하십시오.  
  
-   [방법: C\+\+\/CLI에서 추적 참조 사용](../dotnet/how-to-use-tracking-references-in-cpp-cli.md)  
  
-   [방법: 추적 참조 및 값 형식 사용](../misc/how-to-use-tracking-references-and-value-types.md)  
  
-   [방법: 추적 참조 및 내부 포인터 사용](../misc/how-to-use-tracking-references-and-interior-pointers.md)  
  
-   [방법: 네이티브 매개 변수, 값 매개 변수 또는 참조 매개 변수를 사용하는 템플릿 함수 작성](../misc/how-to-write-template-functions-that-take-native-value-or-reference-parameters.md)  
  
### 예  
 **예제**  
  
 C\+\+\/CLI에 대한 다음 샘플은 네이티브 및 관리되는 형식을 사용하여 추적 참조를 사용하는 방법을 보여 줍니다.  
  
```  
// tracking_reference_1.cpp  
// compile with: /clr  
ref class MyClass {  
public:  
   int i;  
};  
  
value struct MyStruct {  
   int k;  
};  
  
int main() {  
   MyClass ^ x = ref new MyClass;  
   MyClass ^% y = x;   // tracking reference handle to reference object   
  
   int %ti = x->i;   // tracking reference to member of reference type  
  
   int j = 0;  
   int %tj = j;   // tracking reference to object on the stack  
  
   int * pi = new int[2];  
   int % ti2 = pi[0];   // tracking reference to object on native heap  
  
   int *% tpi = pi;   // tracking reference to native pointer  
  
   MyStruct ^ x2 = ref new MyStruct;  
   MyStruct ^% y2 = x2;   // tracking reference to value object  
  
   MyStruct z;  
   int %tk = z.k;   // tracking reference to member of value type  
  
   delete[] pi;  
}  
  
```  
  
 **예제**  
  
 C\+\+\/CLI에 대한 다음 샘플은 배열에 추적 참조를 바인딩하는 방법을 보여 줍니다.  
  
```  
// tracking_reference_2.cpp  
// compile with: /clr  
using namespace System;  
  
int main() {  
   array<int> ^ a = ref new array< Int32 >(5);  
   a[0] = 21;  
   Console::WriteLine(a[0]);  
   array<int> ^% arr = a;  
   arr[0] = 222;  
   Console::WriteLine(a[0]);  
}  
```  
  
 **출력**  
  
  **21**  
 **222**