---
title: "Understanding Parse Trees | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "parse trees"
ms.assetid: 668ce2dd-a1c3-4ca0-8135-b25267cb6a85
caps.latest.revision: 12
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Understanding Parse Trees
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

각 구문 분석 트리는 있는 등록자 스크립트에 하나 이상의 구문 분석 트리를 정의할 수 있습니다.  
  
```  
<root key>{<registry expression>}+  
```  
  
 다음은 각 문자에 대한 설명입니다.  
  
```  
<root key> ::=  HKEY_CLASSES_ROOT | HKEY_CURRENT_USER |  
               HKEY_LOCAL_MACHINE | HKEY_USERS |  
               HKEY_PERFORMANCE_DATA | HKEY_DYN_DATA |  
               HKEY_CURRENT_CONFIG | HKCR | HKCU |  
               HKLM | HKU | HKPD | HKDD | HKCC  
<registry expression> ::= <Add Key> | <Delete Key>  
<Add Key> ::= [ForceRemove | NoRemove | val]<Key Name>  
              [<Key Value>][{< Add Key>}]  
<Delete Key> ::=  Delete<Key Name>  
<Key Name> ::= '<AlphaNumeric>+'  
<AlphaNumeric> ::= any character not NULL, i.e. ASCII 0  
<Key Value> ::== <Key Type><Key Name>  
<Key Type> ::= s | d  
<Key Value> ::= '<AlphaNumeric>'  
```  
  
> [!NOTE]
>  `HKEY_CLASSES_ROOT`및 `HKCR` 같습니다.  `HKEY_CURRENT_USER`및 `HKCU` 같습니다. 합니다.  
  
 구문 분석 트리는 \< 루트 \> 키를 여러 키와 하위 키를 추가할 수 있습니다.  파서가 모든 하위 구문 분석 완료 될 때까지 과정에서 하위 키의 핸들을 열어 둡니다.  이 방법은 다음 예제와 같이 한 번에 하나의 키를 운영 체제 보다 더 효율적입니다.  
  
```  
HKEY_CLASSES_ROOT  
{  
   'MyVeryOwnKey'  
   {  
      'HasASubKey'  
      {  
         'PrettyCool?'  
      }  
   }  
}  
```  
  
 여기에서 등록 자가 처음에 열립니다 \(만듭니다\) `HKEY_CLASSES_ROOT\MyVeryOwnKey`.  다음은 표시 `MyVeryOwnKey` 하위 키에 있습니다.  키를 닫을 것이 아니라 `MyVeryOwnKey`, 등록자 핸들을 유지 하 고 열립니다 \(만듭니다\) `HasASubKey` 이 상위 핸들을 사용 하 여.  \(부모 핸들이 없습니다 열려 있을 때 시스템 레지스트리 느려질 수 있습니다.\) 따라서 열기 `HKEY_CLASSES_ROOT\MyVeryOwnKey` 하 고 여 `HasASubKey` 와 `MyVeryOwnKey` 부모 열기 보다 빠른 이므로 `MyVeryOwnKey`를 `MyVeryOwnKey`, 및 다음 열기 `MyVeryOwnKey\HasASubKey`.  
  
## 참고 항목  
 [Creating Registrar Scripts](../atl/creating-registrar-scripts.md)