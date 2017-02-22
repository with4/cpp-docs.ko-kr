---
title: "file_status 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "filesystem/std::tr2::sys::file_status"
  - "filesystem/std::tr2::sys::file_status::perms"
  - "filesystem/std::tr2::sys::file_status::type"
dev_langs: 
  - "C++"
ms.assetid: 9781840e-ad22-44dd-ad79-0fabaa94bac4
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# file_status 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[file\_type](../Topic/file_type%20Enumeration.md)을 래핑합니다.  
  
## 구문  
  
```  
class file_status;  
```  
  
## file\_status::file\_status  
  
```  
explicit file_status(file_type ftype = file_type::none,    perms mask = perms::unknown) noexcept;file_status(const file_status&) noexcept = default;file_status(file_status&&) noexcept = default;  
```  
  
## file\_status::operator\=  
  
```  
file_status& operator=(const file_status&) noexcept = default;  
file_status& operator=(file_status&&) nexcept = default;  
```  
  
 기본 멤버 대입 연산자가 예상대로 작동합니다.  
  
## type  
  
```  
file_type type() const noexcept  
void type(file_type _Ftype) noexcept  
```  
  
 file\_type을 가져오거나 설정합니다.  
  
## permissions  
  
```  
perms permissions() const noexcept  
void permissions(perms_Prms) noexcept   
```  
  
 파일 사용 권한을 가져오거나 설정합니다.  
  
 setter를 사용하여 파일을 읽기 전용으로 만들거나 읽기 전용 특성을 제거합니다.  
  
## 요구 사항  
 **헤더:** filesystem  
  
 **네임스페이스:** std::tr2::sys  
  
## 참고 항목  
 [헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)   
 [path 클래스\(C\+\+ 표준 템플릿 라이브러리\)](../standard-library/path-class-cpp-standard-template-library.md)   
 [\<filesystem\>](../standard-library/filesystem.md)