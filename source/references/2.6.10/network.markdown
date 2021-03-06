---
layout: default
title: Network Reference
---

# Network Reference



**This page is autogenerated; any changes will get overwritten** *(last generated on Wed Oct 05 10:58:49 -0700 2011)*


This is a list of all Puppet network interfaces.  Each interface is
implemented in the form of a client and a handler; the handler is loaded
on the server, and the client knows how to call the handler's methods
appropriately.

Most handlers are meant to be started on the server, usually within
`puppet master`, and the clients are mostly started on the client,
usually within `puppet agent`.

You can find the server-side handler for each interface at
`puppet/network/handler/<name>.rb` and the client class at
`puppet/network/client/<name>.rb`.

## CA

Provides an interface for signing CSRs.  Accepts a CSR and returns
the CA certificate and the signed certificate, or returns nil if
the cert is not signed.

:Prefix: puppetca
:Side: Server
:Methods: getcert


## FileBucket

The interface to Puppet's FileBucket system.  Can be used to store
files in and retrieve files from a filebucket.

:Prefix: puppetbucket
:Side: Server
:Methods: addfile, getfile


## FileServer

The interface to Puppet's fileserving abilities.

:Prefix: fileserver
:Side: Server
:Methods: describe, list, retrieve


## Master

Puppet's configuration interface.  Used for all interactions related to
generating client configurations.

:Prefix: puppetmaster
:Side: Server
:Methods: getconfig, freshness


## Report

Accepts a Puppet transaction report and processes it.

:Prefix: puppetreports
:Side: Server
:Methods: report


## Runner

An interface for triggering client configuration runs.

:Prefix: puppetrunner
:Side: Client
:Methods: run


## Status

A simple interface for testing Puppet connectivity.

:Prefix: status
:Side: Client
:Methods: status




----------------

*This page autogenerated on Wed Oct 05 10:58:49 -0700 2011*
