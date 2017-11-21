---
title: "filesystem_error 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: filesystem/std::experimental::filesystem::filesystem_error
dev_langs: C++
ms.assetid: c53aac27-c1fa-43e4-8967-48ea8ba1f172
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0012a895dbda27ce26d50ae49b3752d13963a89f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="filesystemerror-class"></a>filesystem_error 클래스
하위 수준 시스템 오버플로를 보고하기 위해 throw되는 모든 예외에 대한 기본 클래스입니다.  
  
## <a name="syntax"></a>구문  
  
```  
class filesystem_error    : public system_error;  
```  
  
## <a name="remarks"></a>설명  
 이 클래스는 \<filesystem> 함수의 오류를 보고하기 위해 throw된 모든 예외에 대한 기본 클래스로 사용됩니다. 문자열 형식의 개체를 저장하며, 여기서는 표시를 위해 mymesg라고 합니다. 또한 mypval1 및 mypval2라는 경로 형식의 두 개체를 저장합니다.  
  
## <a name="filesystemerrorfilesystemerror"></a>filesystem_error::filesystem_error  
  
```  
filesystem_error(const string& what_arg,
    error_code ec);

filesystem_error(const string& what_arg,  
    const path& pval1,
    error_code ec);

filesystem_error(const string& what_arg,  
    const path& pval1,
    const path& pval2,
    error_code ec);
```  
  
 첫 번째 생성자는 what_arg 및 ec에서 메시지를 생성합니다. 두 번째 생성자는 또한 mypval1에 저장되는 pval1에서 해당 메시지를 생성합니다. 세 번째 생성자 또한 mypval1에 저장되는 pval1 및 mypval2에 저장되는 pval2에서 해당 메시지를 생성합니다.  
  
## <a name="filesystemerrorpath1"></a>filesystem_error::path1  
  
```  
const path& path1() const noexcept;  
```  
  
 멤버 함수는 mypval1을 반환합니다.  
  
## <a name="filesystemerrorpath2"></a>filesystem_error::path2  
  
```  
const path& path2() const noexcept;  
```  
  
 멤버 함수는 mypval2를 반환합니다.  
  
## <a name="filesystemerrorwhat"></a>filesystem_error::what  
  
```  
const char *what() const noexcept;  
```  
  
 멤버 함수는 가급적 runtime_error::what(), system_error::what(), mymesg, mypval1.native_string() 및 mypval2.native_string()으로 구성되는 NTBS에 대한 포인터를 반환합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<파일 시스템 >  
  
 **네임스페이스:** std::experimental::filesystem  
  
## <a name="see-also"></a>참고 항목  
 [헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)   
 [system_error 클래스](../standard-library/system-error-class.md)   
 [\<filesystem>](../standard-library/filesystem.md)   
 [\<exception>](../standard-library/exception.md)

