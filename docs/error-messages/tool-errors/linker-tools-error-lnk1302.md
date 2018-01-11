---
title: "링커 도구 오류 LNK1302 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK1302
dev_langs: C++
helpviewer_keywords: LNK1302
ms.assetid: aea3c753-c2c4-4249-bbc3-f2d4f0164b5e
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2a5b9201608d6d457288c7ade9376147da08bcb9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk1302"></a>링커 도구 오류 LNK1302
안전한 .netmodules 링크만 지원됩니다. .netmodule 파일을 링크할 수 없습니다.  
  
 .Netmodule (사용 하 여 컴파일된 **/LN**) MSIL 링크 호출 하려는 사용자 시도가 링커로 전달 되었습니다.  C + + 모듈을 사용 하 여 컴파일한 MSIL 링크에 대 한 유효한 **/clr: safe**합니다.  
  
 이 오류를 해결 하려면 사용 하 여 컴파일하고 **/clr: safe** MSIL 링크를 사용 하도록 설정 하거나 전달 하는 **/clr** 또는 **/clr: 순수** 모듈 대신 링커에.obj 파일입니다.  
  
 자세한 내용은 다음 항목을 참조하세요.  
  
-   [/LN (MSIL 모듈 만들기)](../../build/reference/ln-create-msil-module.md)  
  
-   [링커 입력 파일로 사용하는 .netmodule 파일](../../build/reference/netmodule-files-as-linker-input.md)