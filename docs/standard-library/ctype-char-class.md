---
title: "ctype &lt; char &gt; 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ctype<char>"
  - "locale/std::ctype<char>"
  - "std::ctype<char>"
  - "std.ctype<char>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "< char > ctype 클래스"
ms.assetid: ee30acb4-a743-405e-b3d4-13602092da84
caps.latest.revision: 20
caps.handback.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# ctype &lt; char &gt; 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

클래스는 템플릿 클래스의 명시적 특수화 **ctype \< CharType**> 형식으로 `char`, 형식의 문자의 다양 한 속성의 특징을 지정 하는 로캘 패싯으로 사용할 수 있는 개체를 설명 하는 `char`합니다.  
  
## <a name="syntax"></a>구문  
  
```  
template <>  
class ctype<char>  
: public ctype_base  
{  
public:  
    typedef char _Elem;  
    typedef _Elem char_type;  
    bool is(
    mask _Maskval,  
    _Elem _Ch) const;

 
    const _Elem* is(
    const _Elem* first,  
    const _Elem* last,  
    mask* dest) const;

 
    const _Elem* scan_is(
    mask _Maskval,  
    const _Elem* first,  
    const _Elem* last) const;

 
    const _Elem* scan_not(
    mask _Maskval,  
    const _Elem* first,  
    const _Elem* last) const;

 
    _Elem tolower(
    _Elem _Ch) const;

 
    const _Elem* tolower(
    _Elem* first,  
    const _Elem* last) const;

 
    _Elem toupper(
    _Elem _Ch) const;

 
    const _Elem* toupper(
    _Elem* first,  
    const _Elem* last) const;

 
    _Elem widen(
    char _Byte) const;

 
    const _Elem* widen(
    const char* first,  
    const char* last,  
    _Elem* dest) const;

 
    const _Elem* _Widen_s(
    const char* first,  
    const char* last,  
    _Elem* dest,  
    size_t dest_size) const;

 
    _Elem narrow(
    _Elem _Ch,  
    char _Dflt = '\0') const;

 
    const _Elem* narrow(
    const _Elem* first,  
    const _Elem* last,  
    char _Dflt,  
    char* dest) const;

 
    const _Elem* _Narrow_s(
    const _Elem* first,  
    const _Elem* last,  
    char _Dflt,  
    char* dest,  
    size_t dest_size) const;

 
    static locale::id& id;  
    explicit ctype(
    const mask* _Table = 0,  
    bool _Deletetable = false,  
    size_t _Refs = 0);

protected:  
    virtual ~ctype();
//other protected members  
};  
```  
  
## <a name="remarks"></a>주의  
 명시적 특수화는 여러 가지 방법으로 템플릿 클래스에서 다릅니다.  
  
-   Ctype 클래스의 개체 < `char`> UCHAR_MAX 배열을 + 1 개 요소 형식의 ctype 마스크 테이블의 첫 번째 요소에 대 한 포인터를 저장 **ctype_base::mask**합니다. 배열 삭제 되어야 할지 여부를 나타내는 Boolean 개체를 저장 합니다 (사용 하 여 `operator delete[]`) 때는 ctype \< **Elem**> 개체는 소멸 됩니다.  
  
-   유일한 공용 생성자를 사용 하면 지정 **탭**, ctype 마스크 테이블 및 **del**, Boolean 개체 배열 해야 하면 true를 삭제는 ctype < `char`> 참조 횟수 매개 변수 refs 뿐만 아니라 개체 소멸 합니다.  
  
-   보호 된 멤버 함수 **테이블** 저장된 ctype 마스크 테이블을 반환 합니다.  
  
-   정적 멤버 개체 **table_size** ctype 마스크 테이블의 최소 요소 수를 지정 합니다.  
  
-   보호 된 정적 멤버 함수 **classic_table**(반환 ctype 마스크 테이블 "C" 로캘에 적합 합니다.  
  
-   보호 된 가상 멤버 함수가 없는 [do_is](../standard-library/ctype-class.md#ctype__do_is), [do_scan_is](../standard-library/ctype-class.md#ctype__do_scan_is), 또는 [do_scan_not](../standard-library/ctype-class.md#ctype__do_scan_not)합니다. 해당 공용 멤버 함수 자체 동일한 작업을 수행 합니다.  
  
 멤버 함수는 [do_narrow](../standard-library/ctype-class.md#ctype__do_narrow) 및 [do_widen](../standard-library/ctype-class.md#ctype__do_widen) 도 동일 하 게 하는 요소를 복사 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \< 로캘>  
  
 **네임 스페이스:** std  
  
## <a name="see-also"></a>참고 항목  
 [facet 클래스](../Topic/facet%20Class.md)   
 [ctype_base 클래스](../standard-library/ctype-base-class.md)   
 [C + + 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)

