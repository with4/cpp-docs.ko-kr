---
title: ATL 등록자 및 기초로 Nauer 구성 (bnf 표기법) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- BNF notation
- Backus Nauer Form (BNF) syntax
ms.assetid: 994bbef0-9077-4aa8-bdfe-b7e830af9acc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4137dd94886456d5813076f3cb328bac5ecf5c03
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="understanding-backus-nauer-form-bnf-syntax"></a>기초로 Nauer BNF (Form) 구문을 이해
ATL 등록자에서 사용 하는 스크립트는 다음 표에 표시 된 표기법을 사용 하 여 BNF 구문을 사용 하 여이 항목에 설명 되어 있습니다.  
  
|규칙/기호|의미|  
|------------------------|-------------|  
|`::=`|해당 항목|  
|`&#124;`|또는|  
|`X+`|하나 이상의 `X`s입니다.|  
|`[X]`|`X`는 선택적 요소입니다. 선택적 구분 기호는 `[]`합니다.|  
|모든 **굵게** 텍스트|문자열 리터럴입니다.|  
|모든 *기울임꼴* 텍스트|리터럴 문자열을 생성 하는 방법.|  
  
 위의 표에 나와 있는 것 처럼 등록자 스크립트 문자열 리터럴을 사용 합니다. 이러한 값은 스크립트에 표시 되어야 하는 실제 텍스트입니다. 다음 표에서 ATL 등록자 스크립트에 사용 되는 문자열 리터럴을 설명 합니다.  
  
|문자열 리터럴|작업|  
|--------------------|------------|  
|**ForceRemove**|(있는 경우) 다음 키를 완전히 제거 하 고 다시 만듭니다.|  
|**NoRemove**|등록 취소 하는 동안 다음 키를 제거 하지 않습니다.|  
|**val**|지정 하는 `<Key Name>` 명명된 된 값이 실제로 됩니다.|  
|**삭제**|등록 하는 동안 다음 키를 삭제합니다.|  
|**s**|다음 값을 문자열 임을 지정 (**REG_SZ**).|  
|**d**|다음 값이 되도록 지정는 **DWORD** (**REG_DWORD**).|  
|**m**|다음 값을 문자열 임을 지정 (**REG_MULTI_SZ**).|  
|**b**|다음 값을 이진 값 임을 지정 (**REG_BINARY**).|  
  
## <a name="bnf-syntax-examples"></a>BNF 구문 예제  
 표기법 및 문자열 리터럴에 ATL 등록자 스크립트에서 작동 하는 방식을 쉽게 이해할 수 있도록 몇 가지 구문 예제는 다음과 같습니다.  
  
### <a name="syntax-example-1"></a>구문 예 1  
  
```  
<registry expression> ::= <Add Key>  
```  
  
 지정 하는 `registry expression` 같습니다 `Add Key`합니다.  
  
### <a name="syntax-example-2"></a>구문 예 2  
  
```  
<registry expression> ::= <Add Key> | <Delete Key>  
```  
  
 지정 하는 `registry expression` 동일 `Add Key` 또는 `Delete Key`합니다.  
  
### <a name="syntax-example-3"></a>구문 예 3  
  
```  
<Key Name> ::= '<AlphaNumeric>+'  
```  
  
 지정 하는 `Key Name` 하나 이상에 해당 `AlphaNumerics`합니다.  
  
### <a name="syntax-example-4"></a>구문 예 4  
  
```  
<Add Key> ::= [ForceRemove | NoRemove | val]<Key Name>  
```  
  
 지정 하는 `Add Key` 같습니다 `Key Name`, 하 고 문자열 리터럴, `ForceRemove`, `NoRemove`, 및 `val`는 선택 사항입니다.  
  
### <a name="syntax-example-5"></a>구문 예 5  
  
```  
<AlphaNumeric> ::= any character not NULL, that is, ASCII 0  
```  
  
 지정 하는 `AlphaNumeric` 모든 비 NULL 문자에 해당 합니다.  
  
### <a name="syntax-example-6"></a>구문 예 6  
  
```  
val 'testmulti' = m 'String 1\0String 2\0'  
```  
  
 지정 하는 키 이름을 `testmulti` 다중 문자열 값으로 구성 됩니다 `String 1` 및 `String 2`합니다.  
  
### <a name="syntax-example-7"></a>구문 예 7  
  
```  
val 'testhex' = d '&H55'  
```  
  
 지정 하는 키 이름을 `testhex` 는 **DWORD** 값은 16 진수 55 (10 진수 85)으로 설정 합니다. 참고가이 형식을 준수 하는 **& H** 표기법으로 Visual Basic 사양에서 찾을 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [등록자 스크립트 만들기](../atl/creating-registrar-scripts.md)

