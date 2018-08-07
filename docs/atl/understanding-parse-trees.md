---
title: ATL 등록자 및 구문 분석 트리 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- parse trees
ms.assetid: 668ce2dd-a1c3-4ca0-8135-b25267cb6a85
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bb5b132e5e55ab5336254acaf4d2d3ae25440697
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32358834"
---
# <a name="understanding-parse-trees"></a>구문 분석 트리 이해
각 구문 분석 트리의 형식은 등록자 스크립트에서 하나 이상의 구문 분석 트리를 정의할 수 있습니다.  
  
```  
<root key>{<registry expression>}+  
```  
  
 다음은 각 문자에 대한 설명입니다.  
  
```  
<root key> ::= HKEY_CLASSES_ROOT | HKEY_CURRENT_USER |  
    HKEY_LOCAL_MACHINE | HKEY_USERS |  
    HKEY_PERFORMANCE_DATA | HKEY_DYN_DATA |  
    HKEY_CURRENT_CONFIG | HKCR | HKCU |  
    HKLM | HKU | HKPD | HKDD | HKCC  
<registry expression> ::= <Add Key> | <Delete Key>  
<Add Key> ::= [ForceRemove | NoRemove | val]<Key Name>  
 [<Key Value>][{<Add Key>}]  
<Delete Key> ::= Delete<Key Name>  
<Key Name> ::= '<AlphaNumeric>+'  
<AlphaNumeric> ::= any character not NULL, i.e. ASCII 0  
<Key Value> ::== <Key Type><Key Name>  
<Key Type> ::= s | d  
<Key Value> ::= '<AlphaNumeric>'  
```  
  
> [!NOTE]
> `HKEY_CLASSES_ROOT` 및 `HKCR` 동일 합니다. `HKEY_CURRENT_USER` 및 `HKCU` ; 동일 하며 까지입니다.  
  
 구문 분석 트리 여러 키와 하위 키에 추가할 수는 \<루트 키 >입니다. 이 과정에서 유지 하위 키의 핸들 열기 파서가 모든 하위 키를 구문 분석을 완료 될 때까지 됩니다. 다음 예제와 같이이 방법은 한 번에 단일 키에서 작동 하는 보다 더 효율적입니다.  
  
```  
HKEY_CLASSES_ROOT  
{  
 'MyVeryOwnKey'  
 {  
 'HasASubKey'  
 {  
 'PrettyCool'  
 }  
 }  
}  
```  
  
 여기에서 등록자를 처음 열 (만듭니다) `HKEY_CLASSES_ROOT\MyVeryOwnKey`합니다. 그런 다음 발견 하는 `MyVeryOwnKey` 하위 키가 있습니다. 키를 닫을 것이 아니라 `MyVeryOwnKey`, 등록자 핸들 유지 되 고 열립니다 (만듭니다) `HasASubKey` 이 부모 핸들을 사용 합니다. (시스템 레지스트리에 낮아질 수 있습니다 부모 핸들이 없으면 열릴 때.) 따라서 열기 `HKEY_CLASSES_ROOT\MyVeryOwnKey` 을 여는 경우 및 `HasASubKey` 와 `MyVeryOwnKey` 부모 여 보다 빠르게 그대로 `MyVeryOwnKey`닫는, `MyVeryOwnKey`, 고을 여는 `MyVeryOwnKey\HasASubKey`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [등록자 스크립트 만들기](../atl/creating-registrar-scripts.md)

