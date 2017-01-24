---
title: "directory_entry 클래스 | Microsoft Docs"
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
  - "filesystem/std::tr2::sys::directory_entry"
  - "FILESYSTEM/std::experimental::filesystem::v1::directory_entry::operator const std::experimental::filesystem::v1::path &"
  - "FILESYSTEM/std::experimental::filesystem::v1::directory_entry::directory_entry"
  - "std::experimental::filesystem::v1::directory_entry::directory_entry"
  - "FILESYSTEM/std::experimental::filesystem::v1::directory_entry::operator="
  - "std::experimental::filesystem::v1::directory_entry::operator="
  - "FILESYSTEM/std::experimental::filesystem::v1::directory_entry::assign"
  - "std::experimental::filesystem::v1::directory_entry::assign"
  - "FILESYSTEM/std::experimental::filesystem::v1::directory_entry::replace_filename"
  - "std::experimental::filesystem::v1::directory_entry::replace_filename"
  - "FILESYSTEM/std::experimental::filesystem::v1::directory_entry::path"
  - "std::experimental::filesystem::v1::directory_entry::path"
  - "FILESYSTEM/std::experimental::filesystem::v1::directory_entry::status"
  - "std::experimental::filesystem::v1::directory_entry::status"
  - "FILESYSTEM/std::experimental::filesystem::v1::directory_entry::symlink_status"
  - "std::experimental::filesystem::v1::directory_entry::symlink_status"
  - "FILESYSTEM/std::experimental::filesystem::v1::directory_entry::operator<"
  - "std::experimental::filesystem::v1::directory_entry::operator<"
  - "FILESYSTEM/std::experimental::filesystem::v1::directory_entry::operator=="
  - "std::experimental::filesystem::v1::directory_entry::operator=="
  - "FILESYSTEM/std::experimental::filesystem::v1::directory_entry::operator!="
  - "std::experimental::filesystem::v1::directory_entry::operator!="
  - "FILESYSTEM/std::experimental::filesystem::v1::directory_entry::operator<="
  - "std::experimental::filesystem::v1::directory_entry::operator<="
  - "FILESYSTEM/std::experimental::filesystem::v1::directory_entry::operator>"
  - "std::experimental::filesystem::v1::directory_entry::operator>"
  - "FILESYSTEM/std::experimental::filesystem::v1::directory_entry::operator>="
  - "std::experimental::filesystem::v1::directory_entry::operator>="
dev_langs: 
  - "C++"
ms.assetid: 1827c67b-4137-4548-adb0-f955f7acaf08
caps.latest.revision: 17
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# directory_entry 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`*X`에서 반환하는 개체에 대해 설명합니다. 여기서 *X*는 [directory\_iterator](../standard-library/directory-iterator-class.md) 또는 [recursive\_directory\_iterator](../standard-library/recursive-directory-iterator-class.md)입니다.  
  
## 구문  
  
```  
class directory_entry;  
```  
  
## 설명  
 클래스는 [path 클래스](../standard-library/path-class-cpp-standard-template-library.md) 형식의 개체를 저장합니다.`path`는 [path](../standard-library/path-class-cpp-standard-template-library.md) 또는 `path`에서 파생된 형식일 수 있습니다. 또한 두 개의 [file\_type](../Topic/file_type%20Enumeration.md) 값도 저장합니다. 하나는 저장된 파일 이름의 상태에 대해 알려진 정보를 나타내고, 다른 하나는 파일 이름의 기호화된 링크 상태에 대해 알려진 정보를 나타냅니다.  
  
 자세한 내용 및 코드 예제를 보려면 [파일 시스템 탐색\(C\+\+\)](../standard-library/file-system-navigation.md)를 참조하세요.  
  
## assign  
  
```  
void assign(const PFX path& pval,  
    file_status stat_arg = file_status(),  
    file_status symstat_arg = file_status());  
```  
  
 멤버 함수는 mypath에 pval을, mystat에 stat를, mysymstat에 symstat를 할당합니다.  
  
## directory\_entry  
  
```  
directory_entry() = default;  
directory_entry(const directory_entry&) = default;  
directory_entry(directory_entry&&) noexcept = default;  
explicit directory_entry(const PFX path& pval,  
    file_status stat_arg = file_status(),  
    file_status symstat_arg = file_status());  
```  
  
 기본 생성자는 예상대로 작동합니다. 네 번째 생성자는 mypath를 pval로, mystat를 stat\_arg로, mysymstat를 symstat\_arg로 초기화합니다.  
  
## operator\!\=  
  
```  
bool operator!=(const directory_entry& right) const noexcept;  
  
```  
  
 멤버 함수는 \!\(\*this \=\= right\)를 반환합니다.  
  
## operator\=  
  
```  
directory_entry& operator=(const directory_entry&) = default;  
directory_entry& operator=(directory_entry&&) noexcept = default;  
  
```  
  
 기본 멤버 대입 연산자가 예상대로 작동합니다.  
  
## operator\=\=  
  
```  
bool operator==(const directory_entry& right) const noexcept;  
```  
  
 멤버 함수는 mypath \=\= right.mypath를 반환합니다.  
  
## operator\<  
  
```  
  
bool operator<(const directory_entry& right) const noexcept;  
  
```  
  
 멤버 함수는 mypath \< right.mypath를 반환합니다.  
  
## operator\<\=  
  
```  
bool operator<=(const directory_entry& right) const noexcept;  
```  
  
 멤버 함수는 \!\(right \< \*this\)를 반환합니다.  
  
## operator\>  
  
```  
bool operator>(const directory_entry& right) const noexcept;  
```  
  
 멤버 함수는 right \< \*this를 반환합니다.  
  
## operator\>\=  
  
```  
bool operator>=(const directory_entry& right) const noexcept;  
  
```  
  
 멤버 함수는 \!\(\*this \< right\)를 반환합니다.  
  
## operator const path\_type&  
  
```  
operator const path&() const; // retained  
```  
  
 멤버 연산자는 mypath를 반환합니다.  
  
## path  
  
```  
const PFX path& path() const noexcept;  
```  
  
 멤버 함수는 mypath를 반환합니다.  
  
## replace\_filename  
  
```  
void replace_filename(const PFX path& pval,  
    file_status stat_arg = file_status(),  
    file_status symstat_arg = file_status());  
```  
  
 멤버 함수는 mypath를 mypath.parent\_path\(\) \/ pval로, mystat를 stat\_arg로, mysymstat를 symstat\_arg로 바꿉니다.  
  
## status  
  
```  
file_status status() const;  
file_status status(  
    error_code& ec) const noexcept;  
Otherwise, mystat = status(mypval).  
  
```  
  
 두 멤버 함수는 다음과 같이 먼저 변경될 수 있는 mystat를 반환합니다.  
  
1.  status\_known\(mystat\)이면 아무 작업도 수행하지 않습니다.  
  
2.  그렇지 않고 \!status\_known\(mysymstat\) && \!is\_symlink\(mysymstat\)이면 mystat \= mysymstat입니다.  
  
## symlink\_status  
  
```  
file_status symlink_status() const;  
file_status symlink_status(  
    error_code& ec) const noexcept;  
```  
  
 두 멤버 함수는 다음과 같이 먼저 변경될 수 있는 mysymstat를 반환합니다. status\_known\(mysymstat\)이면 아무 작업도 수행하지 않습니다. 그렇지 않으면  mysymstat \= symlink\_status\(mypval\)입니다.  
  
## 요구 사항  
 **헤더:** filesystem  
  
 **네임스페이스:** std::tr2::sys  
  
## 참고 항목  
 [헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)   
 [\<filesystem\>](../standard-library/filesystem.md)