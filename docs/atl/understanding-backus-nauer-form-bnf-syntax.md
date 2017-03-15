---
title: "Understanding Backus Nauer Form (BNF) Syntax | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Backus Nauer Form (BNF) syntax"
  - "BNF notation"
ms.assetid: 994bbef0-9077-4aa8-bdfe-b7e830af9acc
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# Understanding Backus Nauer Form (BNF) Syntax
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ATL 등록자에서 사용 되는 스크립트는 다음 표에 나와 있는 표기법을 사용 하는 BNF 구문을 사용 하 여이 항목에 설명 되어 있습니다.  
  
|규칙\/기호|의미|  
|------------|--------|  
|`::=`|해당 값|  
|`&#124;`|또는|  
|`X+`|하나 이상의 `X`s.|  
|`[X]`|`X`은 선택적 요소입니다.  선택적 구분 기호에서 `[]`.|  
|모든  **굵은** 텍스트|리터럴 문자열입니다.|  
|모든  *기울임꼴* 텍스트|문자열 리터럴을 만드는 방법에 설명 합니다.|  
  
 위의 표에서 알 수 있듯이 등록자 스크립트 문자열 리터럴을 사용 합니다.  이러한 값은 스크립트에 표시 해야 하는 실제 텍스트입니다.  다음 표에서 ATL 등록자 스크립트에서 사용 되는 문자열 리터럴을 설명 합니다.  
  
|문자열 리터럴|동작|  
|-------------|--------|  
|**ForceRemove**|다음 키 \(있는 경우\)를 완전히 제거 하 고 다시 만듭니다.|  
|**NoRemove**|등록 취소 중에 다음 키를 제거 하지 않습니다.|  
|**val 함수**|지정 하는 `<Key Name>` 실제로 명명 된 값입니다.|  
|**Delete**|등록 하는 동안 다음 키를 삭제합니다.|  
|**s**|다음 값을 문자열 임을 지정 \(**REG\_SZ**\).|  
|**d**|다음 값으로 지정 된  **DWORD**  \(**REG\_DWORD**\).|  
|**m**|다음 값을 문자열 지정 \(**REG\_MULTI\_SZ**\).|  
|**b**|다음 값이 이진 값 지정 \(**REG\_BINARY**\).|  
  
## BNF 구문 예제  
 다음은 ATL 등록자 스크립트에서 표기법과 문자열 리터럴의 작동 방식을 이해 하는 데 도움이 되는 몇 가지 구문 예제입니다.  
  
### 구문 예제 1  
  
```  
<registry expression> ::= <Add Key>  
```  
  
 지정 하는 `registry expression` 같습니다 `Add Key`.  
  
### 구문 예제 2  
  
```  
<registry expression> ::= <Add Key> | <Delete Key>  
```  
  
 지정 하는 `registry expression` 에 해당 하는 `Add Key` 또는 `Delete Key`.  
  
### 구문 예제 3  
  
```  
<Key Name> ::= '<AlphaNumeric>+'  
```  
  
 지정 하는 `Key Name` 하나 이상에 해당 하는 `AlphaNumerics`.  
  
### 구문 예제 4  
  
```  
<Add Key> ::= [ForceRemove | NoRemove | val]<Key Name>  
```  
  
 지정 하는 `Add Key` 같습니다 `Key Name`, 그리고 문자열 리터럴 `ForceRemove`, `NoRemove`, 및 `val`, 선택 사항입니다.  
  
### 구문 예제 5  
  
```  
<AlphaNumeric> ::= any character not NULL, that is, ASCII 0  
```  
  
 지정 하는 `AlphaNumeric` 모든 비\-NULL 문자에 해당 합니다.  
  
### 구문 예제 6  
  
```  
val 'testmulti' = m 'String 1\0String 2\0'  
```  
  
 지정 된 키 이름 `testmulti` multistring 값으로 구성 된 `String 1` 및 `String 2`.  
  
### 구문 예제 7  
  
```  
val 'testhex' = d '&H55'  
```  
  
 지정 키 이름을 `testhex` 되는  **DWORD**  값을 16 진수 55 \(85 10 진수\)로 설정 합니다.  참고가이 형식을 준수 하는  **& H** 표기법으로 Visual Basic 사양에서 찾을 수 있습니다.  
  
## 참고 항목  
 [Creating Registrar Scripts](../atl/creating-registrar-scripts.md)