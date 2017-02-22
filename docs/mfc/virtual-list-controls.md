---
title: "가상 목록 컨트롤 | Microsoft Docs"
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
  - "캐시, 가상 목록 컨트롤 항목 데이터"
  - "list 컨트롤, 목록 보기"
  - "list 컨트롤, virtual"
  - "가상 목록 컨트롤"
ms.assetid: 319f841f-e426-423a-8276-d93f965b0b45
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# 가상 목록 컨트롤
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

A virtual list control is a list view control that has the **LVS\_OWNERDATA** style.  This style enables the control to support an item count up to a `DWORD` \(the default item count only extends to an `int`\).  However, the biggest advantage provided by this style is the ability to only have a subset of data items in memory at any one time.  This allows the virtual list view control to lend itself for use with large databases of information, where specific methods of accessing data are already in place.  
  
> [!NOTE]
>  In addition to providing virtual list functionality in `CListCtrl`, MFC also provides the same functionality in the [CListView](../mfc/reference/clistview-class.md) class.  
  
 There are some compatibility issues you should be aware of when developing virtual list controls.  For more information, see the Compatibility Issues section of the List\-View Controls topic in the [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  
  
## Handling the LVN\_GETDISPINFO Notification  
 Virtual list controls maintain very little item information.  Except for the item selection and focus information, all item information is managed by the owner of the control.  Information is requested by the framework via a **LVN\_GETDISPINFO** notification message.  To provide the requested information, the owner of the virtual list control \(or the control itself\) must handle this notification.  This can easily be done using the Properties window \(see [Mapping Messages to Functions](../mfc/reference/mapping-messages-to-functions.md)\).  The resultant code should look something like the following example \(where `CMyDialog` owns the virtual list control object and the dialog is handling the notification\):  
  
 [!code-cpp[NVC_MFCControlLadenDialog#23](../mfc/codesnippet/CPP/virtual-list-controls_1.cpp)]  
  
 In the handler for the **LVN\_GETDISPINFO** notification message, you must check to see what type of information is being requested.  가능한 값은 다음과 같습니다.  
  
-   `LVIF_TEXT` The `pszText` member must be filled in.  
  
-   `LVIF_IMAGE` The `iImage` member must be filled in.  
  
-   **LVIF\_INDENT** The *iIndent* member must be filled in.  
  
-   `LVIF_PARAM` The *lParam* member must be filled in. \(Not present for sub\-items.\)  
  
-   `LVIF_STATE` The *state* member must be filled in.  
  
 You should then supply whatever information is requested back to the framework.  
  
 The following example \(taken from the body of the notification handler for the list control object\) demonstrates one possible method by supplying information for the text buffers and image of an item:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#24](../mfc/codesnippet/CPP/virtual-list-controls_2.cpp)]  
  
## Caching and Virtual List Controls  
 Because this type of list control is intended for large data sets, it is recommended that you cache requested item data to improve retrieval performance.  The framework provides a cache\-hinting mechanism to assist in optimizing the cache by sending an **LVN\_ODCACHEHINT** notification message.  
  
 The following example updates the cache with the range passed to the handler function.  
  
 [!code-cpp[NVC_MFCControlLadenDialog#25](../mfc/codesnippet/CPP/virtual-list-controls_3.cpp)]  
  
 For more information on preparing and maintaining a cache, see the Cache Management section of the List\-View Controls topic in the [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  
  
## Finding Specific Items  
 The **LVN\_ODFINDITEM** notification message is sent by the virtual list control when a particular list control item needs to be found.  The notification message is sent when the list view control receives quick key access or when it receives an **LVM\_FINDITEM** message.  Search information is sent in the form of an **LVFINDINFO** structure, which is a member of the **NMLVFINDITEM** structure.  Handle this message by overriding the `OnChildNotify` function of your list control object and inside the body of the handler, check for the **LVN\_ODFINDITEM** message.  If found, perform the appropriate action.  
  
 You should be prepared to search for an item that matches the information given by the list view control.  You should return the index of the item if successful, or \-1 if no matching item is found.  
  
## 참고 항목  
 [CListCtrl 사용](../mfc/using-clistctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)