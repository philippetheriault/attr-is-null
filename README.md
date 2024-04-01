# attr-is-null
UGS - Cannot invoke “javax.swing.text.AttributeSet.getAttribute(Object)” because “attr” is null

Hi guys!

I am using UGS Platform 2.1.6 on Windows 10, 64 bits. I have a homemade CNC machine with an Arduino controller.

With UGS, I am able to home and jog the machine and to get it performs gcode commands by tapping them in the console bar.

Unfortunately, I am unable to load gcode files into UGS. 

I did a very sample gcode program (square) to investigate the issue. When I load the file, I see appearing very briefly the square in the Visualizer window. But I am unable to run it. It is like nothing was loaded.

Surprisingly, the exact same program works fine on Candle and the machine is doing what it is supposed to do.

This is the error I get a the bottom it says: Loaded file: 0 rows

When I click on the red icon beside:  Unexpected Exception
Cannot invoke “javax.swing.text.AttributeSet.getAttribute(Object)” because “attr” is null

When I click to get more info it says:

A java.lang.NullPointerException exception has occurred.

However, the system should continue working without further problems.

Click Show Details for the stack trace 

I then see the following:

java.lang.NullPointerException: Cannot invoke "javax.swing.text.AttributeSet.getAttribute(Object)" because "attr" is null
	at org.netbeans.modules.editor.fold.ui.CodeFoldingSideBar.resolveBackColor(CodeFoldingSideBar.java:353)
	at org.netbeans.modules.editor.fold.ui.CodeFoldingSideBar.updateColors(CodeFoldingSideBar.java:368)
	at org.netbeans.modules.editor.fold.ui.CodeFoldingSideBar.access$200(CodeFoldingSideBar.java:99)
	at org.netbeans.modules.editor.fold.ui.CodeFoldingSideBar$2.preferenceChange(CodeFoldingSideBar.java:231)
	at org.netbeans.modules.editor.fold.ui.CodeFoldingSideBar.addNotify(CodeFoldingSideBar.java:287)
	at java.desktop/java.awt.Container.addNotify(Unknown Source)
	at java.desktop/javax.swing.JComponent.addNotify(Unknown Source)
	at org.netbeans.modules.editor.impl.CustomizableSideBar$WestSidebarHolder.addNotify(CustomizableSideBar.java:288)
	at java.desktop/java.awt.Container.addNotify(Unknown Source)
	at java.desktop/javax.swing.JComponent.addNotify(Unknown Source)
	at java.desktop/java.awt.Container.addNotify(Unknown Source)
	at java.desktop/javax.swing.JComponent.addNotify(Unknown Source)
	at java.desktop/java.awt.Container.addNotify(Unknown Source)
	at java.desktop/javax.swing.JComponent.addNotify(Unknown Source)
	at java.desktop/java.awt.Container.addImpl(Unknown Source)
	at java.desktop/java.awt.Container.add(Unknown Source)
	at org.openide.text.CloneableEditorInitializer.initCustomEditor(CloneableEditorInitializer.java:523)
	at org.openide.text.CloneableEditorInitializer.initCustomEditorAndDecorationsInEDT(CloneableEditorInitializer.java:573)
[catch] at org.openide.text.CloneableEditorInitializer.run(CloneableEditorInitializer.java:321)
	at org.openide.text.CloneableEditorInitializer.processPendingEDTRequests(CloneableEditorInitializer.java:135)
	at org.openide.text.CloneableEditorInitializer.waitForFinishedInitialization(CloneableEditorInitializer.java:103)
	at org.openide.text.CloneableEditor.getEditorPane(CloneableEditor.java:673)
	at org.netbeans.core.spi.multiview.text.MultiViewEditorElement.getEditorPane(MultiViewEditorElement.java:146)
	at com.willwinder.ugs.nbp.editor.SourceMultiviewElement.componentActivated(SourceMultiviewElement.java:81)
	at org.netbeans.core.multiview.MultiViewPeer.peerComponentActivated(MultiViewPeer.java:353)
	at org.netbeans.core.multiview.MultiViewCloneableTopComponent.componentActivated(MultiViewCloneableTopComponent.java:124)
	at org.openide.windows.WindowManager.activateComponent(WindowManager.java:266)
	at org.netbeans.core.windows.WindowManagerImpl.lambda$notifyRegistryTopComponentActivated$1(WindowManagerImpl.java:1214)
	at org.netbeans.modules.openide.util.NbMutexEventProvider$Event.doEvent(NbMutexEventProvider.java:97)
	at org.netbeans.modules.openide.util.NbMutexEventProvider$Event.readAccess(NbMutexEventProvider.java:72)
	at org.netbeans.modules.openide.util.LazyMutexImplementation.readAccess(LazyMutexImplementation.java:66)
	at org.openide.util.Mutex.readAccess(Mutex.java:242)
	at org.netbeans.core.windows.WindowManagerImpl.notifyRegistryTopComponentActivated(WindowManagerImpl.java:1213)
	at org.netbeans.core.windows.Central.activateModeTopComponent(Central.java:1786)
	at org.netbeans.core.windows.WindowManagerImpl.topComponentRequestActive(WindowManagerImpl.java:1378)
	at org.openide.windows.TopComponent.requestActive(TopComponent.java:837)
	at org.openide.windows.CloneableOpenSupport$1.run(CloneableOpenSupport.java:83)
	at org.netbeans.modules.openide.util.NbMutexEventProvider$Event.doEvent(NbMutexEventProvider.java:97)
	at org.netbeans.modules.openide.util.NbMutexEventProvider$Event.writeAccess(NbMutexEventProvider.java:62)
	at org.netbeans.modules.openide.util.LazyMutexImplementation.writeAccess(LazyMutexImplementation.java:56)
	at org.openide.util.Mutex.writeAccess(Mutex.java:292)
	at org.openide.windows.CloneableOpenSupport.open(CloneableOpenSupport.java:79)
	at org.openide.text.CloneableEditorSupport.open(CloneableEditorSupport.java:412)
	at com.willwinder.ugs.nbp.core.actions.OpenFileAction.actionPerformed(OpenFileAction.java:61)
	at com.willwinder.ugs.nbp.core.actions.OpenAction.openFile(OpenAction.java:92)
	at java.base/java.util.Optional.ifPresent(Unknown Source)
	at com.willwinder.ugs.nbp.core.actions.OpenAction.actionPerformed(OpenAction.java:87)
	at java.desktop/javax.swing.AbstractButton.fireActionPerformed(Unknown Source)
	at java.desktop/javax.swing.AbstractButton$Handler.actionPerformed(Unknown Source)
	at java.desktop/javax.swing.DefaultButtonModel.fireActionPerformed(Unknown Source)
	at java.desktop/javax.swing.DefaultButtonModel.setPressed(Unknown Source)
	at java.desktop/javax.swing.AbstractButton.doClick(Unknown Source)
	at java.desktop/javax.swing.plaf.basic.BasicMenuItemUI.doClick(Unknown Source)
	at java.desktop/javax.swing.plaf.basic.BasicMenuItemUI$Handler.mouseReleased(Unknown Source)
	at java.desktop/java.awt.Component.processMouseEvent(Unknown Source)
	at java.desktop/javax.swing.JComponent.processMouseEvent(Unknown Source)
	at java.desktop/java.awt.Component.processEvent(Unknown Source)
	at java.desktop/java.awt.Container.processEvent(Unknown Source)
	at java.desktop/java.awt.Component.dispatchEventImpl(Unknown Source)
	at java.desktop/java.awt.Container.dispatchEventImpl(Unknown Source)
	at java.desktop/java.awt.Component.dispatchEvent(Unknown Source)
	at java.desktop/java.awt.LightweightDispatcher.retargetMouseEvent(Unknown Source)
	at java.desktop/java.awt.LightweightDispatcher.processMouseEvent(Unknown Source)
	at java.desktop/java.awt.LightweightDispatcher.dispatchEvent(Unknown Source)
	at java.desktop/java.awt.Container.dispatchEventImpl(Unknown Source)
	at java.desktop/java.awt.Window.dispatchEventImpl(Unknown Source)
	at java.desktop/java.awt.Component.dispatchEvent(Unknown Source)
	at java.desktop/java.awt.EventQueue.dispatchEventImpl(Unknown Source)
	at java.desktop/java.awt.EventQueue$4.run(Unknown Source)
	at java.desktop/java.awt.EventQueue$4.run(Unknown Source)
	at java.base/java.security.AccessController.doPrivileged(Unknown Source)
	at java.base/java.security.ProtectionDomain$JavaSecurityAccessImpl.doIntersectionPrivilege(Unknown Source)
	at java.base/java.security.ProtectionDomain$JavaSecurityAccessImpl.doIntersectionPrivilege(Unknown Source)
	at java.desktop/java.awt.EventQueue$5.run(Unknown Source)
	at java.desktop/java.awt.EventQueue$5.run(Unknown Source)
	at java.base/java.security.AccessController.doPrivileged(Unknown Source)
	at java.base/java.security.ProtectionDomain$JavaSecurityAccessImpl.doIntersectionPrivilege(Unknown Source)
	at java.desktop/java.awt.EventQueue.dispatchEvent(Unknown Source)
	at org.netbeans.core.TimableEventQueue.dispatchEvent(TimableEventQueue.java:136)
	at java.desktop/java.awt.EventDispatchThread.pumpOneEventForFilters(Unknown Source)
	at java.desktop/java.awt.EventDispatchThread.pumpEventsForFilter(Unknown Source)
	at java.desktop/java.awt.EventDispatchThread.pumpEventsForHierarchy(Unknown Source)
	at java.desktop/java.awt.EventDispatchThread.pumpEvents(Unknown Source)
	at java.desktop/java.awt.EventDispatchThread.pumpEvents(Unknown Source)
	at java.desktop/java.awt.EventDispatchThread.run(Unknown Source)


Any clue to get around the issue?

Here is the gcode program:

N010 G00;			Rapid mode
N011 G90;			Absolute position mode 
N012 G17;			XY plane select
N013 G54;			Fixture offset 1
N014 G40;			Cutter compensation (tool diameter) cancel
N015 G49;			Length offset cancel
N016 G80;			Canned cycle cancel

N020 G21;			mm
N021 G94;			feed mm/min

N030 G00 Z20.0
N035 G00 X0.0 Y0.0
N040 G00 Z1.0
N045 M3 S1000
N050 G01 Z-5.0 F250
N065 G01 X0.0 Y100.0 F800
N070 G01 X100.0 Y100.0
N075 G01 X100.0 Y0.0
N080 G01 X0.0 Y0.0
N085 G01 Z1.0 F250
N090 M5
N095 G00 Z20.0
M30
%

Many thanks in advance!

Philippe
