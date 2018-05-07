---
title: '방법: C + 열거형 정의 및 사용 + CLI | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- enum class, specifying underlying types
ms.assetid: df8f2b91-b9d2-4fab-9be4-b1d58b8bc570
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: f5c30b679b24e574d359a1f838785f0196f290d1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-define-and-consume-enums-in-ccli"></a>방법: C++/CLI에서 열거형 정의 및 사용
이 항목에서는 열거형 C + + /cli CLI 합니다.  
  
## <a name="specifying-the-underlying-type-of-an-enum"></a>열거형의 내부 형식을 지정  
 기본적으로 기본 유형의 열거형은 `int`합니다.  그러나 서명 되거나 서명 되지 않은 형태의 되도록 형식을 지정할 수 있습니다 `int`, `short`, `long`, `__int32`, 또는 `__int64`합니다.  사용할 수도 있습니다 `char`합니다.  
  
```  
// mcppv2_enum_3.cpp  
// compile with: /clr  
public enum class day_char : char {sun, mon, tue, wed, thu, fri, sat};  
  
int main() {  
   // fully qualified names, enumerator not injected into scope  
   day_char d = day_char::sun, e = day_char::mon;  
   System::Console::WriteLine(d);  
   char f = (char)d;  
   System::Console::WriteLine(f);  
   f = (char)e;  
   System::Console::WriteLine(f);  
   e = day_char::tue;  
   f = (char)e;  
   System::Console::WriteLine(f);  
}  
```  
  
 **출력**  
  
```Output  
sun  
0  
1  
2  
```  
  
## <a name="how-to-convert-between-managed-and-standard-enumerations"></a>관리 되는 및 표준 열거형 간에 변환 하는 방법  
 열거형과 정수 계열 형식; 간의 표준 변환은 없습니다. 캐스트가 필요 합니다.  
  
```  
// mcppv2_enum_4.cpp  
// compile with: /clr  
enum class day {sun, mon, tue, wed, thu, fri, sat};  
enum {sun, mon, tue, wed, thu, fri, sat} day2; // unnamed std enum  
  
int main() {  
   day a = day::sun;  
   day2 = sun;  
   if ((int)a == day2)  
   // or...  
   // if (a == (day)day2)  
      System::Console::WriteLine("a and day2 are the same");  
   else  
      System::Console::WriteLine("a and day2 are not the same");  
}  
```  
  
 **출력**  
  
```Output  
a and day2 are the same  
```  
  
## <a name="operators-and-enums"></a>연산자 및 열거형  
 다음 연산자는 C + 열거형에서 사용할 + CLI:  
  
|연산자|  
|--------------|  
|== != \< > \<= >=|  
|+ -|  
|&#124; ^ & ~|  
|++ --|  
|sizeof|  
  
 연산자 &#124; ^ & ~ + +-기본 bool을 포함 하지 않는 형식은 정수 계열 열거형에 대해서만 정의 됩니다.  두 피연산자 모두 열거형 형식 이어야 합니다.  
  
 컴파일러는 확인 하지 않고 정적 또는 동적; enum 연산의 결과의 열거형의 유효한 열거자의 범위에 없는 값을 작업이 발생할 수 있습니다.  
  
> [!NOTE]
>  C + + 11의 C + 관리 되는 enum 클래스와 크게 다르게 비관리 코드의 열거형 클래스 형식이 소개 + CLI 합니다. 특히, C + + 11 enum 클래스 형식을 지원 하지 않습니다 관리 되는 열거형 클래스 형식으로 동일한 연산자 C + + /CLI, 및 C + + /CLI 소스 코드 제공 해야 관리 되는 열거형의 액세스 가능성 한정자는 클래스 선언 (c이 + 관리 되지 않는 + 구별할 11) enum 클래스를 선언 합니다. C + enum 클래스에 대 한 자세한 내용은 + CLI, C + + /CX, 및 C + + 11에서는 참조 [enum 클래스](../windows/enum-class-cpp-component-extensions.md)합니다.  
  
```  
// mcppv2_enum_5.cpp  
// compile with: /clr  
private enum class E { a, b } e, mask;  
int main() {  
   if ( e & mask )   // C2451 no E->bool conversion  
      ;  
  
   if ( ( e & mask ) != 0 )   // C3063 no operator!= (E, int)  
      ;  
  
   if ( ( e & mask ) != E() )   // OK  
      ;  
}  
```  
  
```  
// mcppv2_enum_6.cpp  
// compile with: /clr  
private enum class day : int {sun, mon};  
enum : bool {sun = true, mon = false} day2;  
  
int main() {  
   day a = day::sun, b = day::mon;  
   day2 = sun;  
  
   System::Console::WriteLine(sizeof(a));  
   System::Console::WriteLine(sizeof(day2));  
   a++;  
   System::Console::WriteLine(a == b);  
}  
```  
  
 **출력**  
  
```Output  
4  
1  
True  
```  
  
## <a name="see-also"></a>참고 항목  
 [enum 클래스](../windows/enum-class-cpp-component-extensions.md)