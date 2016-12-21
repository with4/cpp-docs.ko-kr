---
title: "system_error 클래스 | Microsoft Docs"
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
  - "system_error/std::system_error"
  - "std.system_error"
  - "std::system_error"
  - "system_error"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "system_error 클래스"
ms.assetid: 2eeaacbb-8a4a-4ad7-943a-997901a77f32
caps.latest.revision: 17
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# system_error 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

낮은 수준의 시스템 오류를 보고 하기 위해 발생 하는 모든 예외에 대 한 기본 클래스를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
class system_error : public runtime_error {  
public:  
    explicit system_error(error_code _Errcode,
    const string& _Message = "");

    system_error(error_code _Errcode,
    const char *_Message);

    system_error(error_code::value_type _Errval,  
    const error_category& _Errcat,
    const string& _Message);

    system_error(error_code::value_type _Errval,  
    const error_category& _Errcat,
    const char *_Message);
const error_code& code() const throw();
const error_code& code() const throw();

 };  
```  
  
## <a name="remarks"></a>주의  
 반환한 값 `what` 클래스에 [예외](../standard-library/exception-class1.md) 에서 생성 된 `_Message` 형식의 저장 된 개체 및 [error_code](../standard-library/error-code-class.md) (중 하나 `code` 또는 `error_code(_Errval, _Errcat)`).  
  
 멤버 함수 `code` 저장 된 반환 [error_code](../standard-library/error-code-class.md) 개체입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \< system_error >  
  
 **네임 스페이스:** std  
  
## <a name="see-also"></a>참고 항목  
 [\< system_error >](../standard-library/system-error.md)

