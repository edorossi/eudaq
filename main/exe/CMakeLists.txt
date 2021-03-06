# build main EUDAQ executables (with option to disable them, use 'cmake -DMainExec=OFF ..'
option(BUILD_main "Compile main EUDAQ executables?" ON)
IF(BUILD_main)
  add_executable(ClusterExtractor    src/ClusterExtractor.cxx  )
  add_executable(Converter           src/Converter.cxx         )
  add_executable(ExampleProducer     src/ExampleProducer.cxx   )
  add_executable(ExampleReader       src/ExampleReader.cxx     )
  add_executable(FileChecker         src/FileChecker.cxx       )
  add_executable(IPHCConverter       src/IPHCConverter.cxx     )
  add_executable(MagicLogBook        src/MagicLogBook.cxx      )
  add_executable(OptionExample       src/OptionExample.cxx     )
  add_executable(RunListener         src/RunListener.cxx       )
  add_executable(TestDataCollector   src/TestDataCollector.cxx )
  add_executable(TestLogCollector    src/TestLogCollector.cxx  )
  add_executable(TestMonitor         src/TestMonitor.cxx       )
  add_executable(TestProducer        src/TestProducer.cxx      )
  add_executable(TestReader          src/TestReader.cxx        )
  add_executable(TestRunControl      src/TestRunControl.cxx    )

  set_property(TARGET ClusterExtractor   PROPERTY PROJECT_LABEL "bin_ClusterExtractor") 
  set_property(TARGET Converter          PROPERTY PROJECT_LABEL "bin_Converter") 
  set_property(TARGET ExampleProducer    PROPERTY PROJECT_LABEL "bin_ExampleProducer") 
  set_property(TARGET ExampleReader      PROPERTY PROJECT_LABEL "bin_ExampleReader") 
  set_property(TARGET FileChecker        PROPERTY PROJECT_LABEL "bin_FileChecker") 
  set_property(TARGET IPHCConverter      PROPERTY PROJECT_LABEL "bin_IPHCConverter") 
  set_property(TARGET MagicLogBook       PROPERTY PROJECT_LABEL "bin_MagicLogBook") 
  set_property(TARGET OptionExample      PROPERTY PROJECT_LABEL "bin_OptionExample") 
  set_property(TARGET RunListener        PROPERTY PROJECT_LABEL "bin_RunListener") 
  set_property(TARGET TestDataCollector  PROPERTY PROJECT_LABEL "bin_TestDataCollector") 
  set_property(TARGET TestLogCollector   PROPERTY PROJECT_LABEL "bin_TestLogCollector")
  set_property(TARGET TestMonitor        PROPERTY PROJECT_LABEL "bin_TestMonitor") 
  set_property(TARGET TestProducer       PROPERTY PROJECT_LABEL "bin_TestProducer") 
  set_property(TARGET TestReader         PROPERTY PROJECT_LABEL "bin_TestReader") 
  set_property(TARGET TestRunControl     PROPERTY PROJECT_LABEL "bin_TestRunControl") 




  # ${ADDITIONAL_LIBRARIES} is only set if e.g. the native reader processor is built (EUTelescope/LCIO)
  target_link_libraries(ClusterExtractor    EUDAQ ${EUDAQ_THREADS_LIB} ${ADDITIONAL_LIBRARIES})
  target_link_libraries(Converter           EUDAQ ${EUDAQ_THREADS_LIB} ${ADDITIONAL_LIBRARIES})
  target_link_libraries(ExampleProducer     EUDAQ ${EUDAQ_THREADS_LIB} ${ADDITIONAL_LIBRARIES})
  target_link_libraries(ExampleReader       EUDAQ ${EUDAQ_THREADS_LIB} ${ADDITIONAL_LIBRARIES})
  target_link_libraries(FileChecker         EUDAQ ${EUDAQ_THREADS_LIB} ${ADDITIONAL_LIBRARIES})
  target_link_libraries(IPHCConverter       EUDAQ ${EUDAQ_THREADS_LIB} ${ADDITIONAL_LIBRARIES})
  target_link_libraries(MagicLogBook        EUDAQ ${EUDAQ_THREADS_LIB} ${ADDITIONAL_LIBRARIES})
  target_link_libraries(OptionExample       EUDAQ ${EUDAQ_THREADS_LIB} ${ADDITIONAL_LIBRARIES})
  target_link_libraries(RunListener         EUDAQ ${EUDAQ_THREADS_LIB} ${ADDITIONAL_LIBRARIES})
  target_link_libraries(TestDataCollector   EUDAQ ${EUDAQ_THREADS_LIB} ${ADDITIONAL_LIBRARIES})
  target_link_libraries(TestLogCollector    EUDAQ ${EUDAQ_THREADS_LIB} ${ADDITIONAL_LIBRARIES})
  target_link_libraries(TestMonitor         EUDAQ ${EUDAQ_THREADS_LIB} ${ADDITIONAL_LIBRARIES})
  target_link_libraries(TestProducer        EUDAQ ${EUDAQ_THREADS_LIB} ${ADDITIONAL_LIBRARIES})
  target_link_libraries(TestReader          EUDAQ ${EUDAQ_THREADS_LIB} ${ADDITIONAL_LIBRARIES})
  target_link_libraries(TestRunControl      EUDAQ ${EUDAQ_THREADS_LIB} ${ADDITIONAL_LIBRARIES})


  INSTALL(TARGETS ClusterExtractor  Converter  ExampleProducer  ExampleReader  FileChecker  IPHCConverter  MagicLogBook  OptionExample  RunListener  TestDataCollector  TestLogCollector  TestMonitor  TestProducer  TestReader  TestRunControl 
    RUNTIME DESTINATION bin
    LIBRARY DESTINATION lib
    ARCHIVE DESTINATION lib)

ENDIF(BUILD_main)
