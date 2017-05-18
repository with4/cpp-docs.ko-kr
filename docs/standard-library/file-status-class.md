---
title: "file_status 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- file_status
- filesystem/std::experimental::filesystem::v1::file_status
- filesystem/std::experimental::filesystem::v1::file_status::operator=
- filesystem/std::experimental::filesystem::v1::file_status::type
- filesystem/std::experimental::filesystem::v1::file_status::permissions
dev_langs:
- C++
ms.assetid: 9781840e-ad22-44dd-ad79-0fabaa94bac4
caps.latest.revision: 15
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: 1095fbeeceb33fd9dedf0ad1217eab1a052f5ba1
ms.contentlocale: ko-kr
ms.lasthandoff: 04/29/2017

---
# <a name="filestatus-class"></a>file_status 클래스
[file_type](../standard-library/filesystem-enumerations.md#file_type) 및 파일 [perms](../standard-library/filesystem-enumerations.md#perms)를 래핑합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
class file_status;  
```  
  
## <a name="filestatusfilestatus"></a>file_status::file_status  
  
```cpp  
explicit file_status(  
   file_type ftype = file_type::none,  
   perms mask = perms::unknown) noexcept;  
  
file_status(const file_status&) noexcept = default;  
  
file_status(file_status&&) noexcept = default; 

~file_status() noexcept = default; 
```  
  
## <a name="filestatusoperator"></a>file_status::operator=  
  
```cpp  
file_status& operator=(const file_status&) noexcept = default;  
file_status& operator=(file_status&&) nexcept = default;  
```  
  
 기본 멤버 대입 연산자가 예상대로 작동합니다.  
  
## <a name="type"></a>type  
  
```cpp  
file_type type() const noexcept  
void type(file_type ftype) noexcept  
```  
  
 file_type을 가져오거나 설정합니다.  
  
## <a name="permissions"></a>permissions  
  
```cpp  
perms permissions() const noexcept  
void permissions(perms mask) noexcept   
```  
  
 파일 사용 권한을 가져오거나 설정합니다.  
  
 setter를 사용하여 파일을 읽기 전용으로 만들거나 읽기 전용 특성을 제거합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<파일 시스템 >  
  
 **Namespace:** std::experimental::filesystem, std::experimental::filesystem::v1  
  
## <a name="see-also"></a>참고 항목  
 [헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)   
 [path 클래스](../standard-library/path-class.md)   
 [\<filesystem>](../standard-library/filesystem.md)


