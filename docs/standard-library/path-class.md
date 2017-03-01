---
title: "path 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- filesystem/std::experimental::filesystem::path
dev_langs:
- C++
ms.assetid: 8a1227ca-aeb2-4e0e-84aa-86e34e4f4fe8
caps.latest.revision: 14
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: acc0ecd4edaf1e58977dcbdeb483d497a72bc4c8
ms.openlocfilehash: b6f1fb2eacdc12857978d03ccbd98ee5da3047e5
ms.lasthandoff: 02/24/2017

---
# <a name="path-class"></a>path 클래스
**path** 클래스는 string\_type 형식의 개체(여기서는 표시 편의상 이름이 myname으로 지정됨)를 저장하며 경로 이름으로 사용하는 데 적합합니다. string\_type은 basic\_string\<value_type>과 동일한 의미이며, 여기서 value\_type은 Windows에서는 char와, Posix에서는 wchar_t와 동일한 의미입니다.  
  
 자세한 내용 및 코드 예제를 보려면 [파일 시스템 탐색(C++)](../standard-library/file-system-navigation.md)을 참조하세요.  
  
## <a name="syntax"></a>구문  
  
```  
class path;  
```  
  
## <a name="pathappend"></a>path::append  
  
```  
template <class Source>  
path& append(const Source& source);  
   
template <class InIt>  
path& append(InIt first, InIt last);
```  
  
 멤버 함수는 필요에 따라 변환되고 preferred_separator를 삽입하는 지정된 시퀀스를 mypath에 추가합니다.  
  
## <a name="pathassign"></a>path::assign  
  
```  
template <class Source>  
path& assign(const Source& source);  
  
template <class InIt>  
path& assign(InIt first, InIt last);
```  
  
 멤버 함수는 mypath를 필요에 따라 변환된 지정된 시퀀스로 바꿉니다.  
  
## <a name="pathbegin"></a>path::begin  
  
```  
iterator begin() const;
```  
  
 경로 이름에서 첫 번째 경로 요소를 지정하는 path::iterator(있는 경우)를 반환합니다.  
  
## <a name="pathcstr"></a>path::c_str  
  
```  
const value_type& *c_str() const noexcept;  
```  
  
 mypath의 첫 번째 문자에 대한 포인터를 반환합니다.  
  
## <a name="pathclear"></a>path::clear  
  
```  
void clear() noexcept;  
```  
  
 멤버 함수는 mypath.clear()를 실행합니다.  
  
## <a name="pathcompare"></a>path::compare  
  
```  
int compare(const path& pval) const noexcept;  
int compare(const string_type& str) const;
int compare(const value_type *ptr) const;
```  
  
 첫 번째 함수는 mypath.compare(pval.native())를 반환합니다. 두 번째 함수는 mypath.compare(str)를 반환합니다. 세 번째 함수는 mypath.compare(ptr)를 반환합니다.  
  
## <a name="pathconcat"></a>path::concat  
  
```  
template <class Source>  
path& concat(const Source& source);  
  
template <class InIt>  
path& concat(InIt first, InIt last);
```  
  
 멤버 함수는 필요에 따라 변환되었지만 구분 기호를 삽입하지 않는 지정된 시퀀스를 mypath에 추가합니다.  
  
## <a name="pathconstiterator"></a>path::const_iterator  
  
```  
typedef iterator const_iterator;  
```  
  
 형식은 iterator의 동의어입니다.  
  
## <a name="pathempty"></a>path::empty  
  
```  
bool empty() const noexcept;  
```  
  
 mypath.empty()를 반환합니다.  
  
## <a name="pathend"></a>path::end  
  
```  
iterator end() const;
```  
  
 반복기 형식의 시퀀스의 끝 반복기를 반환합니다.  
  
## <a name="pathextension"></a>path::extension  
  
```  
path extension() const;
```  
  
 다음과 같이 filename() X의 접미사를 반환합니다.  
  
 X == path(".") &#124;&#124; X == path("..")이거나 X에 점이 없는 경우 접미사가 비어 있습니다.  
  
 그렇지 않은 경우 접미사가 맨 오른쪽 점으로 시작되고 해당 점을 포함합니다.  
  
## <a name="pathfilename"></a>path::filename  
  
```  
path filename() const;
```  
  
 myname의 루트 디렉터리 구성 요소(구체적으로는 `empty()  path() : *--end()`)를 반환합니다. 구성 요소는 비어 있을 수 있습니다.  
  
## <a name="pathgenericstring"></a>path::generic_string  
  
```  
template <class Elem,  
    class Traits = char_traits<Elem>,  
    class Alloc = allocator<Elem>>  
  basic_string<Elem, Traits, Alloc>  
    generic_string(const Alloc& al = Alloc()) const;
  
string generic_string() const;
```  
  
 슬래시로 변환된 백슬래시와 함께 `this->string<Elem, Traits, Alloc>(al)`를 반환합니다(Windows).  
  
## <a name="pathgenericu16string"></a>path::generic_u16string  
  
```  
u16string generic_u16string() const;
```  
  
 슬래시로 변환된 백슬래시와 함께 u16string()을 반환합니다(Windows).  
  
## <a name="pathgenericu32string"></a>path::generic_u32string  
  
```  
u32string generic_u32string() const;
```  
  
 슬래시로 변환된 백슬래시와 함께 u32string()을 반환합니다(Windows).  
  
## <a name="pathgenericu8string"></a>path::generic_u8string  
  
```  
string generic_u8string() const;
```  
  
 슬래시로 변환된 백슬래시와 함께 u8string()을 반환합니다(Windows).  
  
## <a name="pathgenericwstring"></a>path::generic_wstring  
  
```  
wstring generic_wstring() const;
```  
  
 슬래시로 변환된 백슬래시와 함께 wstring()을 반환합니다(Windows).  
  
## <a name="pathhasextension"></a>path::has_extension  
  
```  
bool has_extension() const;
```  
  
 !extension().empty()를 반환합니다.  
  
## <a name="pathhasfilename"></a>path::has_filename  
  
```  
bool has_filename() const;
```  
  
 !filename().empty()를 반환합니다.  
  
## <a name="pathhasparentpath"></a>path::has_parent_path  
  
```  
bool has_parent_path() const;
```  
  
 !parent_path().empty()를 반환합니다.  
  
## <a name="pathhasrelativepath"></a>path::has_relative_path  
  
```  
bool has_relative_path() const;
```  
  
 !relative_path().empty()를 반환합니다.  
  
## <a name="pathhasrootdirectory"></a>path::has_root_directory  
  
```  
bool has_root_directory() const;
```  
  
 !root_directory().empty()를 반환합니다.  
  
## <a name="pathhasrootname"></a>path::has_root_name  
  
```  
bool has_root_name() const;
```  
  
 !root_name().empty()를 반환합니다.  
  
## <a name="pathhasrootpath"></a>path::has_root_path  
  
```  
bool has_root_path() const;
```  
  
 !root_path().empty()를 반환합니다.  
  
## <a name="pathhasstem"></a>path::has_stem  
  
```  
bool has_stem() const;
```  
  
 !stem().empty()를 반환합니다.  
  
## <a name="pathisabsolute"></a>path::is_absolute  
  
```  
bool is_absolute() const;
```  
  
 Windows에서는 함수가 has_root_name() && has_root_directory()를 반환합니다. Posix에서는 함수가 has_root_directory()를 반환합니다.  
  
## <a name="pathisrelative"></a>path::is_relative  
  
```  
bool is_relative() const;
```  
  
 !is_absolute()를 반환합니다.  
  
## <a name="pathiterator"></a>path::iterator  
  
```  
class iterator  
   {
   // bidirectional iterator for path  
   typedef bidirectional_iterator_tag iterator_category;  
   typedef path_type value_type;  
   typedef ptrdiff_t difference_type;  
   typedef const value_type *pointer;  
   typedef const value_type& reference;  
   // ...  
   };  
```  
  
 이 클래스는 시퀀스에서 myname의 경로 구성 요소를 지정하는 양방향 상수 반복기를 설명합니다.  
  
1.  루트 이름(있는 경우)  
  
2.  루트 디렉터리(있는 경우)  
  
3.  파일 이름(있는 경우)으로 끝나는 부모 경로(있는 경우)의 나머지 디렉터리 요소    
  
 pval의 경우 경로 형식의 개체입니다.  
  
1.  path::iterator X = pval.begin()은 경로 이름의 첫 번째 경로 요소(있는 경우)를 지정합니다.  
  
2.  X == pval.end()는 X가 구성 요소 시퀀스의 끝을 지나 가리키는 경우 true입니다.  
  
3. *X는 현재 구성 요소와 일치하는 문자열을 반환합니다.  
  
4.  ++X는 시퀀스에서 다음 구성 요소(있는 경우)를 지정합니다.  
  
5.  --X는 시퀀스에서 이전 구성 요소(있는 경우)를 지정합니다.  
  
6.  myname을 변경하면 myname의 요소를 지정하는 모든 반복기가 무효화됩니다.  
  
## <a name="pathmakepreferred"></a>path::make_preferred  
  
```  
path& make_preferred();
```  
  
 멤버 함수는 필요에 따라 각 구분 기호를 preferred_separator로 변환합니다.  
  
## <a name="pathnative"></a>path::native  
  
```  
const string_type& native() const noexcept;  
```  
  
 myname을 반환합니다.  
  
## <a name="pathoperator"></a>path::operator=  
  
```  
path& operator=(const path& right);
path& operator=(path&& right) noexcept;  
  
template <class Source>  
path& operator=(const Source& source);
```  
  
 첫 번째 멤버 연산자는 right.myname을 myname에 복사합니다. 두 번째 멤버 연산자는 right.myname을 myname으로 이동합니다. 세 번째 멤버 연산자는 *this = path(source)와 동일하게 작동합니다.  
  
## <a name="pathoperator"></a>path::operator+=  
  
```  
path& operator+=(const path& right);
path& operator+=(const string_type& str);
path& operator+=(const value_type *ptr);
path& operator+=(value_type elem);
  
template <class Source>  
path& operator+=(const Source& source);
  
template <class Elem>  
path& operator+=(Elem elem);
```  
  
 멤버 함수는 다음 해당 식과 동일하게 작동합니다.  
  
1.  concat(right);  
  
2.  concat(path(str));  
  
3.  concat(ptr);  
  
4.  concat(string_type(1, elem));  
  
5.  concat(source);  
  
6.  concat(path(basic_string\<Elem>(1, elem)));  
  
## <a name="pathoperator"></a>path::operator/=  
  
```  
path& operator/=(const path& right);  
  
template <class Source>  
path& operator/=(const Source& source);
```  
  
 멤버 함수는 다음 해당 식과 동일하게 작동합니다.  
  
1.  append(right);  
  
2.  append(source);  
  
## <a name="pathoperator-stringtype"></a>path::operator string_type  
  
```  
operator string_type() const;
```  
  
 멤버 연산자는 myname을 반환합니다.  
  
## <a name="pathparentpath"></a>path::parent_path  
  
```  
path parent_path() const;
```  
  
 myname의 부모 경로 구성 요소, 특히 filename().native()를 제거한 후 myname의 접두사와 바로 앞의 디렉터리 구분 기호를 반환합니다. 동일하게 begin() != end()이면 operator/=를 연속적으로 적용하여 [begin(), --end()) 범위의 모든 요소를 결합합니다. 구성 요소는 비어 있을 수 있습니다.  
  
## <a name="pathpath"></a>path::path  
  
```  
path();

path(const path& right);
path(path&& right) noexcept;  
  
template <class Source>  
path(const Source& source);
  
template <class Source>  
path(const Source& source, const locale& loc);
  
template <class InIt>  
path(InIt first, InIt last);
  
template <class InIt>  
path(InIt first, InIt last, const locale& loc);
```  
  
 생성자는 모두 다양한 방식으로 myname을 생성합니다.  
  
 path()의 경우 myname()입니다.  
  
 path(const path& right)의 경우 myname(right.myname)입니다.  
  
 path(path&& right)의 경우 myname(right.myname)입니다.  
  
 template\<class Source> path(const Source& source)의 경우 myname(source)입니다.  
  
 template\<class Source> path(const Source& source, const locale& loc)의 경우 myname(source)이며, loc에서 필요한 codecvt 패싯을 가져옵니다.  
  
 template\<class InIt> path(InIt first, InIt last)의 경우 myname(first, last)입니다.  
  
 template\<class InIt> path(InIt first, InIt last, const locale& loc)의 경우 myname(first, last)이며, loc에서 필요한 codecvt 패싯을 가져옵니다.  
  
## <a name="pathpreferredseparator"></a>path::preferred_separator  
  
```  
#if _WIN32_C_LIB  
static constexpr value_type preferred_separator == L'\\';  
#else // assume Posix  
static constexpr value_type preferred_separator == '/';  
#endif // filesystem model now defined  
```  
  
 상수 개체는 호스트 운영 체제에 따라 경로 구성 요소를 구분하는 기본 문자를 제공합니다. 대부분의 Windows 컨텍스트에서는 L'/'을 대신 사용하여 동일하게 허용됩니다.  
  
## <a name="pathrelativepath"></a>path::relative_path  
  
```  
path relative_path() const;
```  
  
 myname의 상대 경로 구성 요소, 특히 root_path().native()를 제거한 후 myname의 접미사와 바로 뒤의 중복 디렉터리 구분 기호를 반환합니다. 구성 요소는 비어 있을 수 있습니다.  
  
## <a name="pathremovefilename"></a>path::remove_filename  
  
```  
path& remove_filename();
```  
  
## <a name="pathreplaceextension"></a>path::replace_extension  
  
```  
path& replace_extension(const path& newext = path());
```  
  
 멤버 함수는 먼저 myname에서 extension().native() 접미사를 제거합니다. 그런 다음 !newext.empty() && newext[0] != dot(여기서 dot은 *path(".").c_str()임)이면 myname에 dot이 추가됩니다. 그런 다음 myname에 newext가 추가됩니다.  
  
## <a name="pathreplacefilename"></a>path::replace_filename  
  
```  
path& replace_filename(const path& pval);
```  
  
 멤버 함수에서 다음을 실행합니다.  
  
```cpp  
remove_filename();

*this /= pval;  
return (*this);
```  
  
## <a name="pathrootdirectory"></a>path::root_directory  
  
```  
path root_directory() const;
```  
  
 myname의 루트 디렉터리 구성 요소를 반환합니다. 구성 요소는 비어 있을 수 있습니다.  
  
## <a name="pathrootname"></a>path::root_name  
  
```  
path root_name() const;
```  
  
 myname의 루트 이름 구성 요소를 반환합니다. 구성 요소는 비어 있을 수 있습니다.  
  
## <a name="pathrootpath"></a>path::root_path  
  
```  
path root_path() const;
```  
  
 myname의 루트 경로 구성 요소, 특히  root_name() / root_directory를 반환합니다. 구성 요소는 비어 있을 수 있습니다.  
  
## <a name="pathstem"></a>path::stem  
  
```  
path stem() const;
```  
  
 myname의 어간 구성 요소, 특히 후행 extension().native()가 제거된 filename().native()를 반환합니다. 구성 요소는 비어 있을 수 있습니다.  
  
## <a name="pathstring"></a>path::string  
  
```  
template <class Elem, class Traits = char_traits<Elem>, class Alloc = allocator<Elem>>  
basic_string<Elem, Traits, Alloc> string(const Alloc& al = Alloc()) const; 
string string() const;
```  
  
 첫 번째(템플릿) 멤버 함수는 mypath에 저장된 시퀀스를 다음과 동일한 방식으로 변환합니다.  
  
1.  string\<char, Traits, Alloc>()의 경우 string()  
  
2.  string\<wchar_t, Traits, Alloc>()의 경우 wstring()  
  
3.  string\<char16_t, Traits, Alloc>()의 경우 u16string()  
  
4.  string\<char32_t, Traits, Alloc>()의 경우 u32string()  
  
 두 번째 멤버 함수는 mypath에 저장된 시퀀스를 char 시퀀스에 대해 호스트 시스템에서 선호하는 인코딩으로 변환하고 string 형식의 개체에 저장된 대로 반환합니다.  
  
## <a name="pathstringtype"></a>path::string_type  
  
```  
typedef basic_string<value_type> string_type;  
```  
  
 형식은 basic_string<value_type>의 동의어입니다.  
  
## <a name="pathswap"></a>path::swap  
  
```  
void swap(path& right) noexcept;  
```  
  
 swap(mypath, right.mypath)를 실행합니다.  
  
## <a name="pathu16string"></a>path::u16string  
  
```  
u16string u16string() const;
```  
  
 멤버 함수는 mypath에 저장된 시퀀스를 UTF-16으로 변환하고 u16string 형식의 개체에 저장된 대로 반환합니다.  
  
## <a name="pathu32string"></a>path::u32string  
  
```  
u32string u32string() const;
```  
  
 멤버 함수는 mypath에 저장된 시퀀스를 UTF-32로 변환하고 u32string 형식의 개체에 저장된 대로 반환합니다.  
  
## <a name="pathu8string"></a>path::u8string  
  
```  
string u8string() const;
```  
  
 멤버 함수는 mypath에 저장된 시퀀스를 UTF-8로 변환하고 u8string 형식의 개체에 저장된 대로 반환합니다.  
  
## <a name="pathvaluetype"></a>path::value_type  
  
```  
#if _WIN32_C_LIB  
typedef wchar_t value_type;  
#else // assume Posix  
typedef char value_type;  
#endif // filesystem model now defined  
```  
  
 형식은 호스트 운영 체제에서 선호하는 경로 요소를 설명합니다.  
  
## <a name="pathwstring"></a>path::wstring  
  
```  
wstring wstring() const;
```  
  
 mypath에 저장된 시퀀스를 wchar_t 시퀀스에 대해 호스트 시스템에서 선호하는 인코딩으로 변환하고 wstring 형식의 개체에 저장된 대로 반환합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** filesystem  
  
 **네임스페이스:** std::experimental::filesystem
  
## <a name="see-also"></a>참고 항목  
 [헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)


