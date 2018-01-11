---
title: "링커 도구 오류 LNK1179 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK1179
dev_langs: C++
helpviewer_keywords: LNK1179
ms.assetid: 4b1536d7-0d3d-4f29-a9c1-6fa5cf6cb665
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 93b042e928331e369d64a45aa27f5f613ce9fc31
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk1179"></a>링커 도구 오류 LNK1179
잘못 되었거나 손상 된 파일: 'filename' COMDAT가 중복  
  
 개체 모듈에는 같은 이름의 두 개 이상의 Comdat 포함 합니다.  
  
 이 오류를 사용 하 여 발생할 수 있습니다 [/H](../../build/reference/h-restrict-length-of-external-names.md), 외부 이름의 길이 제한 하는 고 [/Gy](../../build/reference/gy-enable-function-level-linking.md), Comdat에 함수를 패키지 하 합니다.  
  
## <a name="example"></a>예  
 다음 코드에서 `function1` 및 `function2` 은 처음 8 자에서 동일 합니다. 로 컴파일할 **/Gy** 및 **/H8** 링크 오류가 발생 합니다.  
  
```  
void function1(void);  
void function2(void);  
  
int main() {  
    function1();  
    function2();  
}  
  
void function1(void) {}  
void function2(void) {}  
```