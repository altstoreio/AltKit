cmake_minimum_required(VERSION 3.15.1)

project(AltKit LANGUAGES Swift)

add_library(CAltKit
    Sources/CAltKit/NSError+ALTServerError.h
    Sources/CAltKit/NSError+ALTServerError.m
)

add_library(AltKit
    Sources/AltKit/Extensions/ALTServerError+Conveniences.swift
    Sources/AltKit/Extensions/Result+Conveniences.swift

    Sources/AltKit/Server/Connection.swift
    Sources/AltKit/Server/NetworkConnection.swift
    Sources/AltKit/Server/Server.swift
    Sources/AltKit/Server/ServerConnection.swift
    Sources/AltKit/Server/ServerManager.swift
    Sources/AltKit/Server/ServerProtocol.swift

    Sources/AltKit/Types/CodableServerError.swift
)

target_link_libraries(AltKit PUBLIC CAltKit)
set_property(TARGET AltKit PROPERTY XCODE_ATTRIBUTE_SWIFT_INCLUDE_PATHS "${CMAKE_CURRENT_SOURCE_DIR}/Sources/CAltKit")
