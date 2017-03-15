---
title: "Windows Runtime and Managed Templates (C++ Component Extensions) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "templates, with CLR types"
ms.assetid: cf59d16b-5514-448b-9a95-e0b4fcb616a6
caps.latest.revision: 14
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Windows Runtime and Managed Templates (C++ Component Extensions)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

템플릿은 Windows 런타임 또는 공용 언어 런타임 타입의 프로토 타입을 정의하고 다른 템플릿 형식의 매개 변수를 사용하여 해당 유형의 변화를 인스턴스화 할 수 있습니다.  
  
## 모든 런타임  
 값 또는 참조 형식에서 서식 파일을 만들 수 있습니다.  값 또는 참조 형식 만들기에 대한 자세한 내용은 [Classes and Structs](../windows/classes-and-structs-cpp-component-extensions.md)를 참조하십시오.  
  
 기본 C\+\+  클래스 템플릿에 대한 자세한 내용은 [클래스 템플릿](../cpp/class-templates.md)를 참조하십시오.  
  
## Windows 런타임\(Windows Runtime\)  
 \(이 언어 기능에는 Windows 런타임에만 적용되는 설명이 없습니다.\)  
  
### 요구 사항  
 컴파일러 옵션: **\/ZW**  
  
## 공용 언어 런타임  
 다음 코드 예제에서 설명하는 관리되는 형식에서 클래스 템플릿을 만드는 몇 가지 제한 사항이 있습니다.  
  
### 요구 사항  
 컴파일러 옵션: **\/clr**  
  
### 예제  
 **예제**  
  
 이것은 관리되는 형식의 템플릿 매개 변수가있는 제네릭 형식을 인스턴스화 할 수 있지만 제네릭 형식 템플릿 매개 변수에서 관리 템플릿을 인스턴스화 할 수 없습니다.  즉, 제네릭 형식이 런타임에 확인되기 때문입니다.  자세한 내용은 [Generics and Templates \(Visual C\+\+\)](../windows/generics-and-templates-visual-cpp.md)을 참조하십시오.  
  
```cpp  
// managed_templates.cpp  
// compile with: /clr /c  
  
generic<class T>   
ref class R;   
  
template<class T>   
ref class Z {  
   // Instantiate a generic with a template parameter.  
   R<T>^ r;    // OK  
};  
  
generic<class T>   
ref class R {  
   // Cannot instantiate a template with a generic parameter.  
   Z<T>^ z;   // C3231  
};  
```  
  
 **예제**  
  
 관리 템플릿에 있는 제네릭 형식이나 함수는 중첩할 수 없습니다.  
  
```cpp  
// managed_templates_2.cpp  
// compile with: /clr /c  
  
template<class T> public ref class R {  
   generic<class T> ref class W {};   // C2959  
};  
```  
  
 **예제**  
  
 C \+ \+ \/ CLI 언어 구문을 사용하여 참조 된 어셈블리에 정의 된 템플릿을 액세스 할 수 없습니다,​​ 하지만 리플렉션을 사용할 수 있습니다.  템플릿이 인스턴스화되지 않으면 메타 데이터에 방출되지 않습니다.  템플릿이 인스턴스화될 경우 메타 데이터에 참조된 멤버 함수에만 표시됩니다.  
  
```cpp  
// managed_templates_3.cpp  
// compile with: /clr  
  
// Will not appear in metadata.  
template<class T> public ref class A {};  
  
// Will appear in metadata as a specialized type.  
template<class T> public ref class R {  
public:  
   // Test is referenced, will appear in metadata  
   void Test() {}  
  
   // Test2 is not referenced, will not appear in metadata  
   void Test2() {}  
};  
  
// Will appear in metadata.  
generic<class T> public ref class G { };  
  
public ref class S { };  
  
int main() {  
   R<int>^ r = gcnew R<int>;  
   r->Test();  
}  
```  
  
 **예제**  
  
 부분 특수화 또는 클래스 템플릿의 명시 적 특수화에 클래스의 관리 수정을 변경할 수 있습니다.  
  
```cpp  
// managed_templates_4.cpp  
// compile with: /clr /c  
  
// class template  
// ref class  
template <class T>  
ref class A {};  
  
// partial template specialization  
// value type  
template <class T>  
value class A <T *> {};  
  
// partial template specialization  
// interface  
template <class T>   
interface class A<T%> {};  
  
// explicit template specialization  
// native class  
template <>  
class A <int> {};  
  
```  
  
## 참고 항목  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)