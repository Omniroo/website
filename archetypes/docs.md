+++
date = '{{ .Date }}'
title = '{{ replace .File.ContentBaseName "-" " " | title }}'
description = ''
weight = 10
draft = false
type = 'docs'
menu = 'main'
sidebar = 'docs'
toc = true
tags = []
categories = ['documentation']
versions = ['current', 'v1.0', 'v0.9']
+++

{{ partial "docs-sidebar.html" . }}

# {{ replace .File.ContentBaseName "-" " " | title }}

## Overview

## Features

## Usage

## Configuration

## Examples

## API Reference

## Troubleshooting

## See Also

{{% /docs/sidebar %}}
