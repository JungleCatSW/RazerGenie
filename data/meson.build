# Matrix Layouts
matrixlayoutdir = join_paths(get_option('datadir'), 'razergenie/matrix_layouts')
install_data('matrix_layouts/razerblade16.json', install_dir : matrixlayoutdir)
install_data('matrix_layouts/razerdefault22.json', install_dir : matrixlayoutdir)
install_data('matrix_layouts/razerblade25.json', install_dir : matrixlayoutdir)

# Translations
languages = ['de']  # add new languages here!
translationsdir = join_paths(get_option('datadir'), 'razergenie/translations')
lrelease = find_program(['lrelease-qt5', 'lrelease'])

foreach lang : languages
    custom_target('translation_' + lang,
        output : lang + '.qm',
        input : 'translations/'+lang+'.ts',
        command : [lrelease, '@INPUT@', '-qm', '@OUTPUT@'],
        install : true,
        install_dir : translationsdir)
endforeach
