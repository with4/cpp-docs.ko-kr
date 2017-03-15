---
title: "MFC에서 사용 되는 콜백 함수 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.functions
dev_langs:
- C++
helpviewer_keywords:
- callback functions, MFC
- MFC, callback functions
- functions [C++], callback
- callback functions
ms.assetid: b2a6857c-fdd3-45ec-8fd8-2e71fac77582
caps.latest.revision: 11
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: b4d104fa76347da43c84611672f843511f0f3725
ms.lasthandoff: 02/24/2017

---
# <a name="callback-functions-used-by-mfc"></a>MFC에서 사용하는 콜백 함수
세 가지 콜백 함수는 Microsoft Foundation 클래스 라이브러리에 표시 됩니다. 에 전달 되는 콜백 함수에 대 한 설명을 [cdc:: enumobjects](../../mfc/reference/cdc-class.md#enumobjects), [cdc:: graystring](../../mfc/reference/cdc-class.md#graystring), 및 [cdc:: setabortproc](../../mfc/reference/cdc-class.md#setabortproc) 이 항목을 따릅니다. 콜백 함수는 일반적인 사용에 대 한 이러한 멤버 함수와의 설명 섹션을 참조 합니다. 참고 모든 콜백 함수가 콜백 경계를 넘어 예외를 throw 할 수 있으므로 Windows를 반환 하기 전에 MFC 예외를 트래핑 해야 합니다. 예외에 대 한 자세한 내용은 문서를 참조 하십시오. [예외](../../mfc/exception-handling-in-mfc.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [구조, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)


