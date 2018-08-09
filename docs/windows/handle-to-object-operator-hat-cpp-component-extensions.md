---
title: 개체 연산자 (^) (c + + 구성 요소 확장)에 대 한 핸들 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- ^ handle to object [C++]
ms.assetid: 70c411e6-be57-4468-a944-6ea7be89f392
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b74f4ca4ab2940dde9dfc567b8fa45ea8f03279e
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39642772"
---
# <a name="handle-to-object-operator---c-component-extensions"></a>개체 연산자에 대한 핸들(^)(C++ 구성 요소 확장)
합니다 *핸들 선언 자* (`^`, "햇"으로 발음), 형식이 수정 [지정자](../cpp/overview-of-declarators.md) 선언된 된 개체를 삭제 해야 함을 자동으로 시스템 개체 인지를 확인 함을 의미 하도록 더 이상 액세스할 수 없습니다.  
  
## <a name="accessing-the-declared-object"></a>선언된 개체 액세스  
 핸들 선언자를 사용하여 선언된 변수는 개체에 대한 포인터처럼 동작합니다. 하지만 변수는 전체 개체를 가리키며 개체의 한 멤버를 가리킬 수 없습니다. 또한 포인터 연산을 지원하지 않습니다. 개체에 액세스하려면 간접 연산자(`*`)를 사용하고 개체의 멤버에 액세스하려면 화살표 멤버 액세스 연산자(`->`)를 사용합니다.  
  
## <a name="windows-runtime"></a>Windows 런타임  
 COM을 사용 하 여 컴파일러 *참조 카운팅* 개체가 더 이상 사용 되지 및 삭제할 수 없습니다 하는 경우를 확인 하는 메커니즘입니다. 이러한 기능이 가능한 이유는 Windows 런타임 인터페이스에서 파생된 개체가 실제로 COM 개체이기 때문입니다. 참조 횟수는 개체가 생성 또는 복사될 때 증가하고 개체가 null로 설정되거나 범위를 벗어날 때 감소합니다. 참조 횟수가 0이 되면 개체가 자동으로, 즉시 삭제됩니다.  
  
 핸들 선언자의 장점을 이해하려면 COM에서 개체의 참조 횟수를 명시적으로 관리해야 하며 이 프로세스는 번거로울 뿐만 아니라 오류가 발생하기 쉽다는 점을 알아야 합니다. 즉, 참조 횟수를 증가 및 감소하려면 개체의 AddRef() 및 Release() 메서드를 호출해야 합니다. 하지만 핸들 선언자로 개체를 선언하면 Visual C++ 컴파일러에서 참조 횟수를 자동으로 조정하는 코드를 만듭니다.  
  
 개체를 인스턴스화하는 방법에 대 한 자세한 내용은 [ref n e w](../windows/ref-new-gcnew-cpp-component-extensions.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
 컴파일러 옵션: `/ZW`  
  
## <a name="common-language-runtime"></a>공용 언어 런타임 
 CLR을 사용 하 여 시스템 *가비지 수집기* 개체가 더 이상 사용 되지 및 삭제할 수 없습니다 하는 경우를 확인 하는 메커니즘입니다. 공용 언어 런타임은 개체를 할당하는 힙을 유지 관리하고 프로그램의 관리되는 참조(변수)를 사용하여 힙에서의 개체 위치를 나타냅니다. 더 이상 개체를 사용하지 않으면 힙에 점유된 메모리가 해제됩니다. 가비지 수집기는 해제된 메모리를 더 효율적으로 사용하기 위해 힙을 정기적으로 압축합니다. 힙을 압축하면 힙에서 개체가 이동할 수 있고, 그럴 경우 관리되는 참조에서 참조한 위치가 무효화됩니다. 하지만 가비지 수집기는 관리되는 모든 참조의 위치를 알고 있으며 해당 위치를 자동으로 업데이트하여 힙에서 개체의 현재 위치를 나타냅니다.  
  
 네이티브 C++ 포인터(`*`) 및 참조(`&`)는 관리되는 참조가 아니며 가비지 수집기는 참조하는 주소를 자동으로 업데이트할 수 없습니다. 이 문제를 해결하려면 핸들 선언자를 사용하여 가비지 수집기가 알고 있고 자동으로 업데이트할 수 있는 변수를 지정합니다.  
  
 Visual C++ 2002 및 Visual C++ 2003에서는 관리되는 힙에서 개체를 선언하는 데 `__gc *`가 사용되었습니다.  새 구문에서는 `^` 대신 `__gc *`을 사용합니다.  
  
 자세한 내용은 [방법: 네이티브 형식에 처리 선언](../dotnet/how-to-declare-handles-in-native-types.md)합니다.  
  
### <a name="examples"></a>예제  
  
 이 샘플은 관리되는 힙에서 참조 형식의 인스턴스를 만드는 방법을 보여 줍니다.  이 샘플은 또한 한 가지 핸들을 다른 핸들로 초기화하여 관리되는 가비지-수집 힙의 동일한 개체에서 두 개의 참조를 만들 수 있다는 점을 보여 줍니다. 할당할 [nullptr](../windows/nullptr-cpp-component-extensions.md) 핸들 하나에 개체가 가비지 수집용으로 표시 되지 않습니다.  
  
```cpp  
// mcppv2_handle.cpp  
// compile with: /clr  
ref class MyClass {  
public:  
   MyClass() : i(){}  
   int i;  
   void Test() {  
      i++;  
      System::Console::WriteLine(i);  
   }  
};  
  
int main() {  
   MyClass ^ p_MyClass = gcnew MyClass;  
   p_MyClass->Test();  
  
   MyClass ^ p_MyClass2;  
   p_MyClass2 = p_MyClass;  
  
   p_MyClass = nullptr;  
   p_MyClass2->Test();     
}  
```  
  
```Output  
1  
2  
```  
  
 다음 예제는 개체 형식이 boxed 값 형식인 관리되는 힙에서 개체에 대해 핸들을 선언하는 방법을 보여 줍니다. 또한 boxed 개체에서 값 형식을 가져오는 방법을 보여 줍니다.  
  
```cpp  
// mcppv2_handle_2.cpp  
// compile with: /clr  
using namespace System;  
  
void Test(Object^ o) {  
   Int32^ i = dynamic_cast<Int32^>(o);  
  
   if(i)  
      Console::WriteLine(i);  
   else  
      Console::WriteLine("Not a boxed int");  
}  
  
int main() {  
   String^ str = "test";  
   Test(str);  
  
   int n = 100;  
   Test(n);  
}  
```   
  
```Output  
Not a boxed int  
100  
```  
  
 이 샘플에서는 사용 하 여 일반적인 c + + 관용구는를 `void*` 임의의 개체를 가리키는 포인터로 바뀝니다 `Object^`, 모든 참조 클래스에 대 한 핸들을 포함할 수 있는 합니다. 또한 배열, 대리자 등의 모든 형식을 개체 핸들로 변환할 수 있음을 보여 줍니다.  
  
```cpp  
// mcppv2_handle_3.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Collections;  
public delegate void MyDel();  
ref class MyClass {  
public:  
   void Test() {}  
};  
  
void Test(Object ^ x) {  
   Console::WriteLine("Type is {0}", x->GetType());  
}  
  
int main() {  
   // handle to Object can hold any ref type  
   Object ^ h_MyClass = gcnew MyClass;  
  
   ArrayList ^ arr = gcnew ArrayList();  
   arr->Add(gcnew MyClass);  
  
   h_MyClass = dynamic_cast<MyClass ^>(arr[0]);  
   Test(arr);  
  
   Int32 ^ bi = 1;  
   Test(bi);  
  
   MyClass ^ h_MyClass2 = gcnew MyClass;  
  
   MyDel^ DelInst = gcnew MyDel(h_MyClass2, &MyClass::Test);  
   Test(DelInst);  
}  
```  
  
```Output  
Type is System.Collections.ArrayList  
  
Type is System.Int32  
  
Type is MyDel  
```  
  
 이 샘플은 핸들을 역참조할 수 있으며 역참조된 핸들을 통해 멤버를 액세스할 수 있음을 보여 줍니다.  
  
```cpp  
// mcppv2_handle_4.cpp  
// compile with: /clr  
using namespace System;  
value struct DataCollection {  
private:  
   int Size;  
   array<String^>^ x;  
  
public:  
   DataCollection(int i) : Size(i) {  
      x = gcnew array<String^>(Size);  
      for (int i = 0 ; i < Size ; i++)  
         x[i] = i.ToString();  
   }  
  
   void f(int Item) {  
      if (Item >= Size)  
      {  
         System::Console::WriteLine("Cannot access array element {0}, size is {1}", Item, Size);  
         return;  
      }  
      else  
         System::Console::WriteLine("Array value: {0}", x[Item]);  
   }  
};  
  
void f(DataCollection y, int Item) {  
   y.f(Item);  
}  
  
int main() {  
   DataCollection ^ a = gcnew DataCollection(10);  
   f(*a, 7);   // dereference a handle, return handle's object  
   (*a).f(11);   // access member via dereferenced handle  
}  
```  
  
```Output  
Array value: 7  
  
Cannot access array element 11, size is 10  
```  
  
 이 샘플에 따르면 네이티브 참조 (`&`)에 바인딩할 수 없습니다는 **int** 관리 되는 형식의 멤버도는 **int** 가비지 수집 힙에서 저장 될 수도 있고 네이티브 참조 추적 하지 않습니다 관리 되는 힙에서 개체 이동 합니다. 해결 방법은 로컬 변수를 사용하거나 `&`를 `%`로 변경하여 추적 참조로 만드는 것입니다.  
  
```cpp  
// mcppv2_handle_5.cpp  
// compile with: /clr  
ref struct A {  
   void Test(unsigned int &){}  
   void Test2(unsigned int %){}  
   unsigned int i;  
};  
  
int main() {  
   A a;  
   a.i = 9;  
   a.Test(a.i);   // C2664  
   a.Test2(a.i);   // OK  
  
   unsigned int j = 0;  
   a.Test(j);   // OK  
}  
```  
  
### <a name="requirements"></a>요구 사항  
 컴파일러 옵션: `/clr`  
  
## <a name="see-also"></a>참고 항목  
 [런타임 플랫폼용 구성 요소 확장명](../windows/component-extensions-for-runtime-platforms.md)   
 [추적 참조 연산자](../windows/tracking-reference-operator-cpp-component-extensions.md)