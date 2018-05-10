---
title: '#오류 지시문 (C/c + +) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- '#error'
dev_langs:
- C++
helpviewer_keywords:
- '#error directive'
- preprocessor, directives
- error directive (#error directive)
ms.assetid: d550a802-ff19-4347-9597-688935d23b2b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ba4f0e06798bc6419f8db0471f19588039eb679a
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
---
# <a name="error-directive-cc"></a>#error 지시문 (C/C++)
`#error` 지시문 컴파일 타임에 사용자 지정 오류 메시지를 내보냅니다 하 고 다음 컴파일을 종료 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
#errortoken-string  
```  
  
## <a name="remarks"></a>설명  
 이 지시문에서 오류 메시지에 포함 된 *토큰 문자열* 매개 변수입니다. `token-string` 매개 변수는 매크로 확장이 적용 되지 않습니다. 이 지시어는 프로그램 불일치할 개발자 또는 제약 조건 위반을 알리기 위한 전처리 중 가장 유용 합니다. 다음 예에서는 전처리 하는 동안 처리 되는 오류를 보여 줍니다.  
  
```  
#if !defined(__cplusplus)  
#error C++ compiler required.  
#endif  
```  
  
## <a name="see-also"></a>참고 항목  
 [전처리기 지시문](../preprocessor/preprocessor-directives.md)