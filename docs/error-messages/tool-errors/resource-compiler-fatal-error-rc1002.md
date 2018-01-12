---
title: "리소스 컴파일러 심각한 오류 RC1002 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: RC1002
dev_langs: C++
helpviewer_keywords: RC1002
ms.assetid: b43dfece-0dc3-4d0b-9d8f-509699b9ae80
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5343f0b6c1309dd4229ed6b34e282d6bc1f3f703
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="resource-compiler-fatal-error-rc1002"></a>리소스 컴파일러 심각한 오류 RC1002
힙 공간이 부족 합니다.  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>아래의 해결 방법 따라 수정합니다.  
  
1.  Windows 스왑 파일 공간을 늘리십시오. 스왑 파일 공간 증가 하는 방법에 대 한 자세한 내용은 Windows 도움말에서 가상 메모리를 참조 하십시오.  
  
2.  현재 파일을 더 작은 파일로 분할 하 고 별도로 컴파일하십시오.  
  
3.  다른 프로그램 또는 시스템에서 실행 중인 드라이버를 제거 합니다.