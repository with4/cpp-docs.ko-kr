---
title: _except_handler3 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _except_handler3
apilocation:
- msvcrt.dll
- msvcr90.dll
- msvcr80.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr100.dll
- msvcr110.dll
apitype: DLLExport
f1_keywords:
- _except_handler3
- except_handler3
dev_langs:
- C++
helpviewer_keywords:
- _except_handler3 function
- except_handler3 function
ms.assetid: b0c64898-0ae5-48b7-9724-80135a0813e2
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b4fe280562d4f1278d74ae118712c9167de4b54d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="excepthandler3"></a>_except_handler3
내부 CRT 함수입니다. 프레임워크에서 적절한 예외 처리기를 찾아 현재 예외를 처리하는 데 사용됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
int _except_handler3(  
   PEXCEPTION_RECORD exception_record,  
   PEXCEPTION_REGISTRATION registration,  
   PCONTEXT context,  
   PEXCEPTION_REGISTRATION dispatcher  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 [in] `exception_record`  
 특정 예외에 대한 자세한 정보입니다.  
  
 [in] `registration`  
 예외 처리기를 찾는 데 어떤 범위 테이블을 사용해야 하는지를 나타내는 레코드입니다.  
  
 [in] `context`  
 예약됨.  
  
 [in] `dispatcher`  
 예약됨.  
  
## <a name="return-value"></a>반환 값  
 예외를 해제해야 하는 경우 `DISPOSITION_DISMISS`를 반환합니다. 예외 캡슐화 처리기 수준까지 예외를 전달해야 하는 경우 `DISPOSITION_CONTINUE_SEARCH`를 반환합니다.  
  
## <a name="remarks"></a>설명  
 이 메서드가 적절한 예외 처리기를 찾으면 예외를 처리기에 전달합니다. 이 경우에 이 메서드는 자신을 호출한 코드로 반환되지 않으며 반환 값은 관계가 없습니다.  
  
## <a name="see-also"></a>참고 항목  
 [사전순 함수 참조](../c-runtime-library/reference/crt-alphabetical-function-reference.md)