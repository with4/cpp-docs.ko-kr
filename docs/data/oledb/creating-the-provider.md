---
title: 공급자 만들기 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB providers, creating
ms.assetid: 2506ba8f-010d-4231-aac1-387432f7b6b9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: b08d2a2f68d174ae7c92d1d6bc0fa2bbb764fdca
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33097187"
---
# <a name="creating-the-provider"></a>공급자 만들기
#### <a name="to-create-an-ole-db-provider-with-the-atl-ole-db-provider-wizard"></a>ATL OLE DB 공급자 마법사를 사용 하 여 OLE DB 공급자를 만들려면  
  
1.  프로젝트를 마우스 오른쪽 단추로 클릭 합니다.  
  
2.  바로 가기 메뉴를 클릭 **추가**, 클릭 하 고 **클래스 추가**합니다.  
  
3.  에 **클래스 추가** 대화 상자는 **ATL OLE DB Provider** 아이콘을 클릭 한 다음 **열려**합니다.  
  
4.  ATL OLE DB 공급자 마법사에서 공급자의 약식 이름을 입력 된 **약식 이름** 상자입니다. 다음 항목에서는 "MyProvider" 짧은 이름을 사용 하지만 다른 이름을 사용할 수 있습니다. 다른 이름 상자에 입력 한 이름이 따라 채웁니다.  
  
5.  필요한 경우 다른 이름 입력란을 편집 합니다. 개체 및 파일 이름 외에도 다음을 편집할 수 있습니다.  
  
    -   **Coclass**: COM에서 공급자를 만드는 데 사용할 이름입니다.  
  
    -   **ProgID**: 프로그래밍 방식 식별자는 GUID 대신 사용할 수 있는 텍스트 문자열입니다.  
  
    -   **버전**: 프로그래밍 방식으로 버전 종속 ID를 생성 하려면 ProgID 및 coclass 함께 사용  
  
6.  **마침**을 클릭합니다.  
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 공급자 만들기](../../data/oledb/creating-an-ole-db-provider.md)