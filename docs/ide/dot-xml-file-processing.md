---
title: ".Xml 파일 처리 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "XML 문서, XML 파일 처리"
ms.assetid: e70fdeae-80ac-4872-ab24-771c5635cfbf
caps.latest.revision: 15
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# .Xml 파일 처리
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

컴파일러는 태그가 있는 코드의 각 구문에 ID 문자열을 생성하여 문서를 만듭니다.  자세한 내용은  [태그 문서 주석에 권장 되는](../ide/recommended-tags-for-documentation-comments-visual-cpp.md).  ID 문자열은 해당 구문을 고유하게 식별합니다.  .Xml 파일을 처리 하는 프로그램 설명서에 적용 되는 해당.NET Framework 리플렉션 또는 메타 데이터 항목을 식별 하는 ID 문자열을 사용할 수 있습니다.  
  
 .Xml 파일 코드는 계층적 표현 하지, 각 요소에 대해 생성 된 ID로 목록이 있습니다.  
  
 컴파일러는 아래와 같은 규칙에 따라 ID 문자열을 생성합니다.  
  
-   문자열에 공백 문자를 배치하지 않습니다.  
  
-   ID 문자열의 첫 부분은 식별할 멤버의 종류를 나타내는 단일 문자이며 그 뒤에 콜론이 옵니다.  아래와 같은 멤버 형식을 사용합니다.  
  
    |문자|설명|  
    |--------|--------|  
    |N|네임스페이스<br /><br /> 문서 주석은 네임 스페이스에 추가할 수 없습니다, 그리고 네임 스페이스에 대 한 cref 참조를 사용할 수 있습니다.|  
    |T|형식\(클래스, 인터페이스, 구조체, 열거형, 대리자\)|  
    |D|형식 정의|  
    |F|필드\(field\)|  
    |P|속성\(인덱서와 기타 인덱싱된 속성 포함\)|  
    |M|메서드\(생성자, 연산자 등의 특수한 메서드 포함\)|  
    |E|이벤트|  
    |\!|오류 문자열<br /><br /> 나머지 문자열은 오류 정보를 제공합니다.  Visual C\+\+ 컴파일러는 확인할 수 없는 링크에 대 한 오류 정보를 생성 합니다.|  
  
-   문자열의 둘째 부분은 네임스페이스의 루트에서 시작하는 항목의 정규화된 이름입니다.  이름 항목, 해당 바깥쪽 형식 또는 형식 및 네임 스페이스는 마침표로 구분 합니다.  항목 이름 자체에 마침표가 있는 경우 해당 마침표는 해시 기호\('\#'\)로 바뀝니다.  항목 이름에 직접 해시 기호 있다고 가정 합니다.  예를 들어, 정규화 된 이름에는 `String` 생성자 "System.String.\#ctor"은.  
  
-   속성 및 메서드의 경우, 메서드 인수가 있는 경우 인수 목록을 괄호로 묶어야 합니다.  인수가 없으면 괄호는 필요 없습니다.  인수는 쉼표로 구분합니다.  각 인수의 인코딩은 아래와 같이 .NET Framework 시그니처에서 인수를 인코딩하는 방법을 그대로 따릅니다.  
  
    -   기본 형식.  정규 형식\(ELEMENT\_TYPE\_CLASS 또는 ELEMENT\_TYPE\_VALUETYPE\)은 형식의 정규화된 이름으로 표시됩니다.  
  
    -   내장 형식 \(예를 들어, ELEMENT\_TYPE\_I4, ELEMENT\_TYPE\_OBJECT, ELEMENT\_TYPE\_STRING, ELEMENT\_TYPE\_TYPEDBYREF.  및 ELEMENT\_TYPE\_VOID\) 해당 전체 형식의 정규화 된 이름으로 예를 들어 표현 됩니다  **System.Int32** 또는  **System.TypedReference**.  
  
    -   ELEMENT\_TYPE\_PTR는 수정된 형식 다음에 '\*'을 붙여 표시합니다.  
  
    -   ELEMENT\_TYPE\_BYREF는 수정된 형식 다음에 '@'을 붙여 표시합니다.  
  
    -   ELEMENT\_TYPE\_PINNED는 수정된 형식 다음에 '^'을 붙여 표시합니다.  Visual C\+\+ 컴파일러는 절대로이 생성 됩니다.  
  
    -   ELEMENT\_TYPE\_CMOD\_REQ는 수정된 형식 다음에 '&#124;' 및 한정자 클래스의 정규화된 이름을 붙여 표시합니다.  Visual C\+\+ 컴파일러는 절대로이 생성 됩니다.  
  
    -   ELEMENT\_TYPE\_CMOD\_REQ는 수정된 형식 다음에 '&#124;' 및 한정자 클래스의 정규화된 이름을 붙여 표시합니다.  
  
    -   ELEMENT\_TYPE\_SZARRAY는 배열 요소 형식 다음에 "\[\]"를 붙여 표시합니다.  
  
    -   ELEMENT\_TYPE\_GENERICARRAY는 배열 요소 형식 다음에 "\[?\]"를 붙여 표시합니다.  Visual C\+\+ 컴파일러는 절대로이 생성 됩니다.  
  
    -   ELEMENT\_TYPE\_ARRAY는 \[*lowerbound*:`size`,*lowerbound*:`size`\]의 형식으로 표시합니다. 여기에서, 쉼표의 수는 차수에서 1을 뺀 값이며 알려진 각 차원의 lowerbound와 size는 숫자로 표시됩니다.  lowerbound 또는 size를 지정하지 않으면 생략됩니다.  특정 차원의 lowerbound와 size가 생략되면 ':' 또한 생략됩니다.  예를 들어, lowerbound가 1이고 size가 지정되지 않은 2차원 배열은 \[1:,1:\]입니다.  
  
    -   ELEMENT\_TYPE\_FNPTR는 "\=FUNC:`type`\(*signature*\)"로 나타냅니다. 여기서, `type`은 반환 형식이며 *signature*는 메서드 인수입니다.  인수가 없으면 괄호는 생략합니다.  Visual C\+\+ 컴파일러는 절대로이 생성 됩니다.  
  
     아래와 같은 시그니처 구성 요소는 오버로드된 메서드를 구분하는 데 사용되지 않기 때문에 표시되지 않습니다.  
  
    -   호출 규칙  
  
    -   반환 형식  
  
    -   ELEMENT\_TYPE\_SENTINEL  
  
-   메서드의 반환 값으로 인코딩 변환 연산자에는 ' ~' 반환 형식으로 인코딩된은 앞 뒤에.  
  
-   제네릭 형식의 경우 형식의 이름 뒤에는 역따옴표\(\`\) 및 제네릭 형식 매개 변수의 수를 나타내는 번호가 추가됩니다.  다음 예제를 참조하십시오.  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
     로 정의 된 형식에 대해 `public class MyClass\<T, U>`.  
  
     제네릭 형식을 매개 변수로 사용하는 메서드의 경우 제네릭 형식 매개 변수는 역따옴표\(\`\)가 앞에 추가된 번호로 지정됩니다\(예: \`0, \`1\).  각 번호는 형식의 제네릭 매개 변수에 대한 배열\(0부터 시작\) 표시를 나타냅니다.  
  
## 예제  
 다음 예제에 대 한 클래스 ID 문자열을 어떻게 표시 하 고 해당 멤버가 생성 됩니다.  
  
```  
// xml_id_strings.cpp  
// compile with: /clr /doc /LD  
///   
namespace N {    
// "N:N"  
  
   /// <see cref="System" />  
   //  <see cref="N:System"/>  
   ref class X {      
   // "T:N.X"  
  
   protected:  
      ///   
      !X(){}     
      // "M:N.X.Finalize", destructor's representation in metadata  
  
   public:  
      ///   
      X() {}     
      // "M:N.X.#ctor"  
  
      ///   
      static X() {}     
      // "M:N.X.#cctor"  
  
      ///   
      X(int i) {}     
      // "M:N.X.#ctor(System.Int32)"  
  
      ///   
      ~X() {}     
      // "M:N.X.Dispose", Dispose function representation in metadata  
  
      ///   
      System::String^ q;     
      // "F:N.X.q"  
  
      ///   
      double PI;     
      // "F:N.X.PI"  
  
      ///   
      int f() { return 1; }     
      // "M:N.X.f"  
  
      ///   
      int bb(System::String ^ s, int % y, void * z) { return 1; }  
      // "M:N.X.bb(System.String,System.Int32@,System.Void*)"  
  
      ///   
      int gg(array<short> ^ array1, array< int, 2 >^ IntArray) { return 0; }   
      // "M:N.X.gg(System.Int16[], System.Int32[0:,0:])"  
  
      ///   
      static X^ operator+(X^ x, X^ xx) { return x; }  
     // "M:N.X.op_Addition(N.X,N.X)"  
  
      ///   
      property int prop;     
      // "M:N.X.prop"  
  
      ///   
      property int prop2 {     
      // "P:N.X.prop2"  
  
         ///   
         int get() { return 0; }  
         // M:N.X.get_prop2  
  
         ///   
         void set(int i) {}  
         // M:N.X.set_prop2(System.Int32)  
      }  
  
      ///   
      delegate void D(int i);   
      // "T:N.X.D"  
  
      ///   
      event D ^ d;   
      // "E:N.X.d"  
  
      ///   
      ref class Nested {};   
      // "T:N.X.Nested"  
  
      ///   
      static explicit operator System::Int32 (X x) { return 1; }   
      // "M:N.X.op_Explicit(N.X!System.Runtime.CompilerServices.IsByValue)~System.Int32"  
   };  
}  
```  
  
## 참고 항목  
 [XML 문서](../ide/xml-documentation-visual-cpp.md)