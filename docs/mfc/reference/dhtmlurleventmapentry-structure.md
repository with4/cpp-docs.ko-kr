---
title: DHtmlUrlEventMapEntry 구조체 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- DHtmlUrlEventMapEntry
dev_langs:
- C++
helpviewer_keywords:
- DHtmlUrlEventMapEntry structure [MFC]
ms.assetid: 43117c1f-1a51-406c-aa2f-fea647080049
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ee629d9dcffc80ce20306989cad72d466722af87
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/29/2018
ms.locfileid: "37123333"
---
# <a name="dhtmlurleventmapentry-structure"></a>DHtmlUrlEventMapEntry 구조체
`DHtmlUrlEventMapEntry` 다중 URL 이벤트 맵 지원 구조를 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
struct DHtmlUrlEventMapEntry  
{  
LPCTSTR szUrl;  
const DHtmlEventMapEntry *pEventMap;  
};  
```  
  
#### <a name="parameters"></a>매개 변수  
 *szUrl*  
 URL입니다.  
  
 *pEventMap*  
 URL에 연결 된 이벤트 맵입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxdhtml.h  
  
## <a name="see-also"></a>참고 항목  
 [구조체, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)

