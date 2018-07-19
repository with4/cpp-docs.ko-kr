---
title: NMAKE 심각한 오류 U1051 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- U1051
dev_langs:
- C++
helpviewer_keywords:
- U1051
ms.assetid: fede5cd5-dac3-47b7-b86d-e1acfb78699f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 570c7e5d8e6e8250a67e4f032ac26b04388cfd00
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33317416"
---
# <a name="nmake-fatal-error-u1051"></a>NMAKE 심각한 오류 U1051
메모리 부족  
  
 NMAKE 메이크파일이 너무 크거나 복잡 하기 때문에 가상 메모리를 포함 하 여 메모리 부족 오류가 발생 했습니다.  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>아래의 해결 방법 따라 수정합니다.  
  
1.  디스크 공간을 확보 합니다.  
  
2.  Windows NT 페이징 파일이 나 Windows 스왑 파일의 크기를 늘립니다.  
  
3.  메이크파일의 일부만 사용 중인 경우에 메이크파일의를 별도 파일로 사용 나누거나 **! IF** 전처리 지시문 NMAKE 처리 해야 하는 양을 제한할 수 있습니다. **! IF** 지시문에는 **! IF**, `!IFDEF`, **! IFNDEF**, **! ELSE IF**, **! 다른** `IFDEF`, 및 **! 다른** `IFNDEF`합니다.